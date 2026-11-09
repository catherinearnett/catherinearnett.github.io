---
layout: default
title: Language Report Cards
permalink: /report-cards/
---

# Language Report Cards
{: .no_toc }

Limiting to institutional languages (inspired by [https://aclanthology.org/2024.acl-long.797.pdf](https://aclanthology.org/2024.acl-long.797.pdf)): <span id="rc-count">322</span> unique ISO 639-3 in my set, Official national or regional languages for all countries.

<div class="rc-picker">
  <label for="rc-select"><strong>Choose a language:</strong></label>
  <select id="rc-select" aria-label="Choose a language">
    <option value="">Loading languages…</option>
  </select>
</div>

## Methodological details

<!-- Fill in later. -->
*Coming soon.*

<div id="rc-report" aria-live="polite"></div>

<style>
  .rc-picker { margin: 1.5rem 0; display: flex; flex-wrap: wrap; gap: .5rem; align-items: center; }
  .rc-picker select { font-size: 1rem; padding: .35rem .5rem; max-width: 100%; min-width: 16rem; }
  #rc-report { margin-top: 2rem; border-top: 1px solid #eeebee; padding-top: 1rem; }
  #rc-report:empty { display: none; }
  #rc-report pre { line-height: 1.25; }
  .rc-status { color: #5c5962; font-style: italic; }
</style>

<script>
(function () {
  var BASE = "/report-cards/reports/";
  var select = document.getElementById("rc-select");
  var target = document.getElementById("rc-report");

  function setStatus(text) {
    target.innerHTML = "";
    var p = document.createElement("p");
    p.className = "rc-status";
    p.textContent = text;
    target.appendChild(p);
  }

  function tidy(container) {
    /* Give tables the theme's horizontal-scroll wrapper. */
    container.querySelectorAll("table").forEach(function (t) {
      if (t.parentElement.classList.contains("table-wrapper")) return;
      var w = document.createElement("div");
      w.className = "table-wrapper";
      t.parentNode.insertBefore(w, t);
      w.appendChild(t);
    });
    /* Relative image paths (e.g. img/uzn_uploads.png) are relative to the reports folder. */
    container.querySelectorAll("img").forEach(function (img) {
      var src = img.getAttribute("src") || "";
      if (src && !/^([a-z]+:|\/|#)/i.test(src)) img.setAttribute("src", BASE + src);
    });
    /* External links open in a new tab. */
    container.querySelectorAll("a[href^='http']").forEach(function (a) {
      a.target = "_blank";
      a.rel = "noopener";
    });
  }

  function show(iso) {
    if (!iso) { target.innerHTML = ""; return; }
    setStatus("Loading report…");
    fetch(BASE + encodeURIComponent(iso) + ".html")
      .then(function (r) { if (!r.ok) throw new Error(r.status); return r.text(); })
      .then(function (html) {
        target.innerHTML = html;
        tidy(target);
      })
      .catch(function () { setStatus("Sorry, the report for " + iso + " could not be loaded."); });
  }

  fetch(BASE + "languages.json")
    .then(function (r) { return r.json(); })
    .then(function (langs) {
      document.getElementById("rc-count").textContent = langs.length;
      select.innerHTML = "";
      var first = document.createElement("option");
      first.value = "";
      first.textContent = "Select a language (" + langs.length + ")";
      select.appendChild(first);
      langs.forEach(function (l) {
        var o = document.createElement("option");
        o.value = l.iso;
        o.textContent = l.name + " (" + l.iso + ")";
        select.appendChild(o);
      });
      /* Deep links: /report-cards/#uzn opens the Uzbek report. */
      var fromHash = decodeURIComponent(location.hash.slice(1));
      if (fromHash && langs.some(function (l) { return l.iso === fromHash; })) {
        select.value = fromHash;
        show(fromHash);
      }
    })
    .catch(function () {
      select.innerHTML = '<option value="">Could not load the language list</option>';
    });

  select.addEventListener("change", function () {
    var iso = select.value;
    history.replaceState(null, "", iso ? "#" + iso : location.pathname);
    show(iso);
  });
})();
</script>
