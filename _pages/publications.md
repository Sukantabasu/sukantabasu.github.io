---
layout: page
permalink: /publications/
title: publications
description: Peer-reviewed journal articles, book chapters, and selected conference proceedings, in reverse-chronological order. Group members are <strong>highlighted</strong>. Use the box below to filter by keyword, topic tag, or year.
nav: false
nav_order: 1
---

<!-- _pages/publications.md -->

Full record on [Google Scholar](https://scholar.google.com/citations?user=08bv9p8AAAAJ) and [ORCID](https://orcid.org/0000-0002-0507-5349).

<!-- Bibsearch Feature -->

{% include bib_search.liquid %}

<div class="publications">

{% bibliography %}

</div>

<script>
  // Number journal articles only, continuously and descending: the newest
  // article carries the highest number, the oldest carries 1. Book chapters
  // and conference proceedings are left unnumbered.
  document.addEventListener("DOMContentLoaded", function () {
    var items = document.querySelectorAll(".publications ol.bibliography > li");
    var journalItems = [];
    items.forEach(function (li) {
      if (li.querySelector(".bib-article")) {
        journalItems.push(li);
      } else {
        li.classList.add("bib-unnumbered");
      }
    });
    var n = journalItems.length;
    journalItems.forEach(function (li) {
      var badge = document.createElement("span");
      badge.className = "pub-number";
      badge.textContent = n + ".";
      li.insertBefore(badge, li.firstChild);
      li.classList.add("bib-numbered");
      n--;
    });
  });
</script>
