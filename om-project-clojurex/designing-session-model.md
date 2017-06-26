# Designing Session Model

The conference app is going to display a list of sessions, so we need to model the data for a session.

> #### Note::Model a conference session
> Add the session data to the existing `app-state`
>
> Use an associative data structure (map or vector) to model a conference session

A conference has the following pieces of information

* Title
* Description
* Speaker name
* Speaker biography
* Twitter handle
* Github handle
* Speakers website


<!--sec data-title="Reveal answer..." data-id="answer001" data-collapse=true ces-->

A map can be used to model a single schedule as follows:

```clj
{:title "Opening Keynote"
 :description "Something very inspirational"
 :speaker-name "John Stevenson"
 :speaker-biography "There's a frood who really knows where his towel is."
  :twitter-handle "jr0cket"
  :github-handle "jr0cket"
  :speakers-website "http://jr0cket.co.uk"}
```
<!--endsec-->

