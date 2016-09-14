---
layout: post
title: Per-request Wrapper for Catalyst::View::TT
---

Catalyst::View::TT allows you to define a wrapper that is used for *every* request, which appears to function like a regular Template::Toolkit wrapper:

{% highlight perl %}
package MyApp::View::TT;
...

__PACKAGE__->config(
   WRAPPER => 'wrapper.tt',
);
{% endhighlight %}

However, there is no (documented and encapsulated) way of changing this value on a per-request basis. The particular use-case I had was wanting to "remove" the default wrapper---which contained the site's header and footer---for any AJAX request, as well as for any email sent via Catalyst::View::Email::Template.

My solution was to still use this wrapper, but instead of it actually being a wrapper itself, this wrapper simply wrapped the content in another wrapper:

{% highlight text %}
[%
   DEFAULT wrapper = 'wrapper/default.tt';
   WRAPPER $wrapper; GET content; END;
-%]
{% endhighlight %}

Then, by setting the stash value for "wrapper" to the desired file name, the desired wrapper is used. So in my use case, for this to work for AJAX requests, in MyApp::Controller::Root:

{% highlight perl %}
sub auto :Private {
   ...
   if ($c->req->header('x-requested-with') eq 'XMLHttpRequest') {
      $c->stash->{wrapper} = 'wrapper/bare.tt';
   }
   ...
}
{% endhighlight %}

However, this still wasn't satisfactory for emails, since in the case where an email is sent (e.g., password recovery) and then a page is rendered for the user (e.g. confirmation that the email was sent), the stash value for "wrapper" will have to be set to "wrapper/email.tt", then back to its old value.

Because the stash is localised within the template, my solution here was to put that bit of logic in the dummy wrapper:

{% highlight text %}
[%
   DEFAULT wrapper = 'wrapper/default.tt';
   CALL (wrapper = 'wrapper/email.tt') IF template.name.match('^email/');
   WRAPPER $wrapper; GET content; END;
-%]
{% endhighlight %}
