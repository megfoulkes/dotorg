---
layout: help
title: Help us Improve OpenSpending
---

## Hacking on OpenSpending

### Do you want to help us?

We welcome all hackers who want to contribute code, documentation, translations, issues/bug reports, comments or just about anything to [OpenSpending](http://openspending.org/). With your help OpenSpending can reach its goal of *tracking every government financial transaction across the world*.

When hacking on OpenSpending there are a few important cyberspace places you should know about:

* [the developer mailing list](http://lists.okfn.org/mailman/listinfo/openspending-dev) (where you can find all OpenSpending developers)
* [the IRC channel (#openspending on Freenode)](http://webchat.freenode.net/?channels=openspending) (informal chat and the monthly developer meetings)
* [the repositories](http://github.com/openspending/) (where code and documentation for OpenSpending live)
* [the transifex project](https://www.transifex.com/projects/p/openspending/) (if you want to get your language into OpenSpending)
* [development process](/help/documentation-process.html) (get your contributions into OpenSpending faster by following our process)

### Where can you start?

If you want to code, here's a list of some issues where you can help OpenSpending:

<table id="github-issues" class="table">
  <tr><th>Difficulty</th><th>Issue</th></tr>
</table>

<script src="http://openspending.org/static/openspendingjs/lib/vendor/jquery.js"></script>
<script type="text/javascript">
  var issues = $("#github-issues");
  var github = "https://api.github.com/repos/openspending/openspending/issues"
  var labels = [{name:"volunteer-simple", colour:"#d7e102"},
                {name:"volunteer-advanced", colour:"#e102d8"},
                {name:"volunteer-hard", colour:"#02e10c"}];
  for (idx in labels) {
    var label = labels[idx];
    $.ajax({
      url: github,
      data: {labels:label.name},
      success: function(data) {
        $.each(data, function(i) {
          issues.append('<tr><td>'
                        + '<span class="label" style="background:'
                        + label.colour
                        + '; text-shadow: 0 -1px 0 rgba(0, 0, 0, 0.25);">'
                        + label.name
                        + '</td><td><a href="'
                        + this.html_url
                        + '">'
                        + this.title
                        + '</a></td></tr>'
                       );
        });
      },
      async: false,
    });
  }
</script>
