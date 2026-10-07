---
layout: default
title: About
permalink: /
subtitle: Postdoctoral Researcher @ [TUD](https://theory.chm.tu-dresden.de/members.shtml?name=ccer) & [HZDR](https://www.hzdr.de/db/Cms?pOid=73041&pNid=0) & [CASUS](https://www.casus.science/theory-of-complex-systems/)

profile:
  image: profile_pic.jpg

social: true
---

<link rel="stylesheet" href="{{ '/assets/css/about.css' | relative_url }}">

<div id="theme-toggle-wrapper">
  <button id="page-theme-toggle" type="button" title="Toggle light/dark theme" aria-label="Toggle light/dark theme">
    <span id="page-theme-icon">◐</span>
  </button>
</div>

<script>
document.addEventListener("DOMContentLoaded", function () {
  const button = document.getElementById("page-theme-toggle");
  const icon = document.getElementById("page-theme-icon");

  function updateIcon() {
    const theme = document.documentElement.getAttribute("data-theme");

    if (theme === "dark") {
      icon.textContent = "☀";
      button.title = "Switch to light mode";
    } else {
      icon.textContent = "☾";
      button.title = "Switch to dark mode";
    }
  }

  button.addEventListener("click", function () {
    const theme = document.documentElement.getAttribute("data-theme");

    if (typeof setThemeSetting === "function") {
      setThemeSetting(theme === "dark" ? "light" : "dark");
    }
  });

  updateIcon();

  const observer = new MutationObserver(updateIcon);

  observer.observe(document.documentElement, {
    attributes: true,
    attributeFilter: ["data-theme"]
  });
});
</script>

<!-- ============================================================
     ABOUT
     ============================================================ -->

<section class="about-hero" id="about">

<aside class="about-profile">

  {% assign profile_image_path = page.profile.image | prepend: 'assets/img/' %}

  <img
    class="about-avatar"
    src="{{ profile_image_path | relative_url }}"
    alt="Chen Chen Er"
    loading="eager"
  >

  {% if page.social %}
    <div class="about-social">
      {% social_links %}
    </div>
  {% endif %}

  {% if site.email %}
    <div class="about-email">

      <div>
        <a href="mailto:{{ site.email | encode_email }}">
          {{ site.email }}
        </a>
      </div>

      {% if site.additional_emails %}
        {% for email in site.additional_emails %}
          <div>
            <a href="mailto:{{ email | encode_email }}">
              {{ email }}
            </a>
          </div>
        {% endfor %}
      {% endif %}

    </div>
  {% endif %}

</aside>

  <div class="about-intro">

    <h1 class="about-name">
      {% if site.title == 'blank' %}
        {{ site.first_name }}
        {% if site.middle_name %}
          {{ site.middle_name }}
        {% endif %}
        {{ site.last_name }}
      {% else %}
        {{ site.title }}
      {% endif %}
    </h1>

    <div class="about-subtitle">
      {{ page.subtitle | markdownify }}
    </div>

    <div class="about-copy">

      <p>
        Computational chemist specializing in materials science. My main research
        interests focus on autonomous materials design for energy storage and
        conversion applications.
      </p>

      <p>
        I am currently based at the Chair of Theoretical Chemistry at
        TU Dresden, Germany, as a postdoctoral research fellow under the
        supervision of Dr. Rico Friedrich and Prof. Thomas Heine, with research
        activities at HZDR/CASUS.
      </p>

      <p>
        I completed my PhD in Chemical Engineering at Monash University in
        July 2023 and subsequently worked as a postdoctoral research fellow
        in Singapore from 2023 to 2024. My current research focuses on modelling
        and understanding confined high-entropy disordered materials and their
        interfaces.
      </p>

    </div>

  </div>

</section>


<!-- ============================================================
     RESEARCH NAVIGATION
     ============================================================ -->

<nav class="research-subnav" aria-label="Research sections">

  <a href="#materials-screening">
    Materials Screening and Design
  </a>

  <a href="#high-throughput-tools">
    Development of High-throughput Tools
  </a>

</nav>


<!-- ============================================================
     MATERIALS SCREENING AND DESIGN
     ============================================================ -->

<section
  class="research-section"
  id="materials-screening"
>

  <h2>Catalysis</h2>

  <div class="research-grid">

<div class="research-image">

  <a
    href="https://doi.org/10.1021/acs.chemrev.1c00068"
    target="_blank"
    rel="noopener noreferrer"
    class="research-image-link"
  >
    <img
      src="{{ 'assets/img/rp_graphic_abstract.png' | relative_url }}"
      class="research-cover"
      alt="Computational materials screening"
      loading="eager"
    >
  </a>

</div>

    <div class="research-text">

      <p>
        <strong>
          Energy conversion and storage using renewable energy technologies.
        </strong>
        Processes including conversion into energy-dense carriers
        (<i>e.g.</i>, hydrogen and synthetic fuels), energy storage in batteries,
        and photovoltaic generation of electric power are currently either
        inefficient, insufficiently stable, or reliant on rare or toxic
        materials.
      </p>

      <p>
        My research focuses on identifying bottlenecks in these processes at
        surfaces and interfaces. I apply high-throughput modelling and
        machine-learning approaches to provide guidance for experimental work.
        Together with high-performance computing infrastructure, these methods
        allow me to investigate materials and reaction processes across multiple
        scales, down to their elementary mechanisms.
      </p>

    </div>

  </div>


  <div class="research-refs">

    {% bibliography
      --query @*[key=er2025interpretable]*
      --group_by none
    %}

    {% bibliography
      --query @*[key=er2025unveiling]*
      --group_by none
    %}

    {% bibliography
      --query @*[key=er2022allotropes]*
      --group_by none
    %}

  </div>


  <p class="research-followup">
    With my expertise, I provide theoretical insights and maintain long-term
    collaborations with experimental partners.
  </p>


  <div class="research-refs">

    {% bibliography
      --query @*[key=loh2026nanostructured]*
      --group_by none
    %}

    {% bibliography
      --query @*[key=sinha2026dynamic]*
      --group_by none
    %}

    {% bibliography
      --query @*[key=tang2023two]*
      --group_by none
    %}

  </div>

</section>


<!-- ============================================================
     HIGH-THROUGHPUT TOOLS
     ============================================================ -->
<section
  class="research-section"
  id="high-throughput-tools"
>

  <h2>High-entropy Materials</h2>

  <div class="research-flow">

    <div class="research-float-image">

      <a
        href="https://aflow.org/"
        target="_blank"
        rel="noopener noreferrer"
        class="aflow-logo-link"
      >
        <img
          src="{{ 'assets/img/aflow_logo.png' | relative_url }}"
          class="research-cover"
          alt="AFLOW"
          loading="eager"
        >
      </a>

      <div class="aflow-software-card">
        {% include repository/software_card.liquid
          repository="aflow-org/aflow"
        %}
      </div>

    </div>


    <p>
      The need for improved functionalities under extreme environments is
      driving increasing interest in high-entropy materials, particularly
      ceramics. Although some compositions can be stabilized through
      configurational entropy, the discovery of new high-entropy systems
      remains challenging because of their very large configurational spaces.
    </p>

    <p>
      One proposed approach is to represent chemical disorder using an
      ensemble of ordered structures, as implemented in
      <a
        href="https://pubs.acs.org/doi/abs/10.1021/acs.chemmater.6b01449"
        target="_blank"
        rel="noopener noreferrer"
      >POCC</a>,
      thereby capturing representative microstates of the disordered system.
    </p>

    <p>
      The synthesizability of high-entropy materials is commonly assessed
      using configurational entropy together with formation enthalpies from
      density functional theory. This has motivated simplified descriptors
      such as
      <a
        href="https://www.nature.com/articles/s41467-018-07160-7"
        target="_blank"
        rel="noopener noreferrer"
      >EFA</a>
      and
      <a
        href="https://www.nature.com/articles/s41586-023-06786-y"
        target="_blank"
        rel="noopener noreferrer"
      >DEED</a>,
      as well as
      <a
        href="https://www.nature.com/articles/s41578-021-00340-w"
        target="_blank"
        rel="noopener noreferrer"
      >machine-learning approaches</a>.
    </p>

    <p>
      My current work extends the original POCC methodology toward modelling
      and understanding confined high-entropy materials. Reduced-dimensional
      high-entropy systems are particularly interesting because chemical
      disorder must be considered together with surfaces, interfaces, and
      structural confinement.
    </p>

    <p>
      The broader objective is to develop a high-throughput workflow that can
      be made available to the community through the
      <a
        href="https://aflow.org/"
        target="_blank"
        rel="noopener noreferrer"
      >AFLOW</a>
      framework developed and maintained by Prof.
      <a
        href="https://mems.duke.edu/people/stefano-curtarolo/"
        target="_blank"
        rel="noopener noreferrer"
      >Stefano Curtarolo</a>
      and his team at Duke University.
    </p>

    <p>
      The manuscript describing this work has been submitted and will be
      updated here following publication.
    </p>

  </div>


</section>
