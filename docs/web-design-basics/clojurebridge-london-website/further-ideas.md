# Further content ideas

The site could be developed further as an exercise by the reader. Suggested ideas for new content sections include

- Registration (sign up button, date, location, etc.)
- Current sponsor (details of the current sponsor, sponsor messaging)
- ClojureBridge overview (description of the event)
- Clojure Showcase (some projects that demonstrate what Clojure can do)
- Learning paths (links to the various curriculums)
- Clojure Installation (how to set up a development environment)
- ClojureBridge Schedule (what happens and when)
- Resources (documentation, how to practice clojure, books, videos, etc)
- Coaching guide (documentation to help coaches coach the students)
- Sponsors guide (how to sponsor ClojureBridge and what to get out of it)
- Past events (overview of all previous events, date, location, sponsors, etc.)
- Models of learning (ideas on how to learn more effectively)

Create a function for each content section that will be developed and add call that function from the `landing-page` function.

> ####HINT::Reagent examples
> [Introduction to Reagent](https://reagent-project.github.io/) has many simple examples of functions you can include in the website
>
> [Guide to Reagent](https://purelyfunctional.tv/guide/reagent/) has even more examples


## Create a banner heading using Bootstrap hero style

CSS frameworks have a `hero` or `jumbotron` class for creating a large banner area on a page, highlighting the main concept or theme of the website.

```clojure
(defn website-title []
  [:section {:class "hero"}
   [:h1 (get-in @app-state [:website :title])]
   [:h4 (get-in @app-state [:website :description])]])
```
