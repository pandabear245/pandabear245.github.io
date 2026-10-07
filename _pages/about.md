---
layout: about
title: About
permalink: /
subtitle: Postdoctoral Researchers @ [TUD](https://theory.chm.tu-dresden.de/members.shtml?name=ccer) & [HZDR](https://www.hzdr.de/db/Cms?pOid=73041&pNid=0) & [CASUS](https://www.casus.science/theory-of-complex-systems/) 

profile:
  align: left
  image: profile_pic.jpg
  image_circular: false # crops the image to make it circular
  more_info: >

social: true # includes social icons in the about header
---

<div class="about-layout" id="about">
  <div class="about-left">
    {% assign profile_image_path = page.profile.image | prepend: 'assets/img/' %}
    <img class="about-avatar" src="{{ profile_image_path | relative_url }}" alt="{{ page.profile.image }}" loading="eager">
    <h1 class="about-name">
      {% if site.title == 'blank' %}
        <span class="font-weight-bold">{{ site.first_name }}</span> {{ site.middle_name }}
        {{ site.last_name }}
      {% else %}
        {{ site.title }}
      {% endif %}
    </h1>
    <p class="about-subtitle">{{ page.subtitle }}</p>
    {% if site.email %}
      <p class="about-email">
        <a href="mailto:{{ site.email | encode_email }}">{{ site.email }}</a>
      </p>
    {% endif %}
    {% if page.social %}
      <div class="social">
        <div class="contact-icons">{% include social.liquid %}</div>
        <div class="contact-note">{{ site.contact_note }}</div>
      </div>
    {% endif %}
  </div>
  <div class="about-right">
<div class="about-copy" markdown="1">

Computational Chemist specializing in materials science. Dr. Chen Chen Er's main research interest is
on autonomous materials design for energy storage and conversion applications. He is currently based in the Chair of Theoretical Chemistry (Prof. Thomas Heine) at TU Dresden, Germany, as a postdoctoral research fellow under the direct supervision of Dr. Rico Friedrich and Prof. Thomas D. Kühne. 

He completed his doctoral studies in Chemical Engineering at Monash University in July 2023 and worked as a postdoctoral research fellow in Singapore from 2023 to 2024.  His current research is on modelling and understanding confined high-entropy disordered materials towards designing novel device interfaces.

</div>
  </div>
</div>

<span id="research" class="section-anchor"></span>

<nav class="research-subnav">
  <a href="#catalysis">Materials Screening and Design</a>
  <a href="#complex-chemically-disordered-systems">Development of High-throughput Tools</a>
</nav>

<div class="research-copy" markdown="1">

### Materials Screening and Design

<div class="row">
    <div class="col-md-4 mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/rp_graphic_abstract.png" class="img-fluid rounded z-depth-1 research-cover" alt="Computational materials screening cover" zoomable=true %}
    </div>
<div class="row">
    <div class="col-md-8 mt-3 mt-md-0">
        <p>
              **Energy conversion and storage using renewable energy technologies**. Processes including the conversion into energy dense carriers (i.e., hydrogen and synthetic fuels), the storage in batteries, the photovoltaic generation of electric power, are currently either inefficient or not stable enough, or require rare/toxic materials. My goal is to specifically investigates the bottleneck in these processes at the surfaces and interfaces, for which I then apply high-throughput modelling and machine learning approaches for guidance in experimental works. With the help of these techniques (and high-performance computing infrastructure), I am able to bridge many orders of magnitude and study these processes from the detailed elementary reactions.
        </p>
    </div>
</div>

<div class="row mt-2">
    <div class="col-md-12">
        <div class="research-refs"> 
            {% bibliography --query @*[key=er2025interpretable]* --group_by none --template bib_research_ref %}
            {% bibliography --query @*[key=er2025unveiling]* --group_by none --template bib_research_ref %}
            {% bibliography --query @*[key=er2022allotropes]* --group_by none --template bib_research_ref %}
        </div>
    </div>
</div>

<div class="row mt-3">
    <div class="col-md-12 mt-3 mt-md-0">
        <p>
            With my expertise, I offer theoretical insights and maintain sustainable collaborative works with my experimental partners.
        </p>
    </div>
</div>

<div class="row mt-2">
    <div class="col-md-12">
        <div class="research-refs"> 
            {% bibliography --query @*[key=loh2026nanostructured]* --group_by none --template bib_research_ref %}
            {% bibliography --query @*[key=sinha2026dynamic]* --group_by none --template bib_research_ref %}
            {% bibliography --query @*[key=tang2023two]* --group_by none --template bib_research_ref %}
        </div>
    </div>
</div>

### Development of High-throughput Tools

<div class="row">
    <div class="col-md-4 mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/aflow_logo.png" class="img-fluid rounded z-depth-1 research-cover" alt="AFLOW" zoomable=true %}
    </div>
    <div class="col-md-8 mt-3 mt-md-0">
        <p>
            The need for improved functionalities in extreme environments is fueling interest in high entropy materials, particularly of ceramics. While some compositions can be stabilized by maximizing entropy, still the search for new high-entropy systems is mostly performed using trial-and-error and some intuition. 
            Therefore effective computational discovery is challenged by the large available configurational space. One of the proposed solution is then to model the chemical disorder using an ensemble of ordered structures (_i.e._, [POCC](https://pubs.acs.org/doi/abs/10.1021/acs.chemmater.6b01449)), effectively capturing the microstates of the system. 
            The synthesizability of high entropy materials is typically assessed using ideal entropy along with the formation enthalpies from density functional theory, with simplified descriptors (_e.g._, [EFA](https://www.nature.com/articles/s41467-018-07160-7) or 
            [DEED](https://www.nature.com/articles/s41586-023-06786-y)) or [machine learning methods](https://www.nature.com/articles/s41578-021-00340-w).
            My goal thus far have been to extend the original POCC implementation for modelling and understanding confined high-entropy materials. The interest in this field are readily apparent. For example, up to nine different transition metals were successfully incorporated into the cation sublattices of [MXene](https://doi.org/10.1126/science.adv4415). The plan is to develop a high-throughput workflow that is 
            readily available to the community in the [AFLOW](https://aflow.org/) framework developed and maintained by Prof. [Stefano Curtarolo](https://mems.duke.edu/people/stefano-curtarolo/) and his team in Duke University. The manuscript for this work has been submitted and will be updated and shared in the future.
        <div class="research-refs">
            {% bibliography --query @*[key=tan2023toward]* --group_by none --template bib_research_ref %}
        </div>
    </div>
</div>

<div class="software-grid">
    {% include repository/software_card.liquid repository="aflow-org/aflow" %}
</div>
