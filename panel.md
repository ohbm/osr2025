---
layout: page
title: Panels
---

<html>
<script>

function getPanelSpeakersForPanelName(panelName) {
  // Filter all speakers to select only those that are in the given panel
  const speakers = {{ site.data.speakers | jsonify }};
  const panelSpeakers = speakers.filter(speaker => speaker.Panel !== undefined);
  return panelSpeakers.filter(speaker => (speaker.Panel && speaker.Panel.toLowerCase().includes(panelName.toLowerCase())));
}

function getUrlForSpeaker(speaker) {
  // Take website if available, then twitter, then github
  if (speaker.Website) {
    return speaker.Website;
  }
  if (speaker.Twitter) {
    return speaker.Twitter;
  }
  if (speaker.Github) {
    return speaker.Github;
  }

  return "";
}

function emptyStringForNull(element) {
  // Return empty string if the element is null to prevent the display of "null" on the page
  const out = element ? element : "";
  return out;
}

function getImageAssetPathForSpeaker(speaker) {
  // Retrieve image path of the speaker photo
  return `../img/speakers/${speaker.Name.toLowerCase().replaceAll(' ', '_')}.jpg`;
}

function formatSpeakerDiv(speaker) {
  // Generate a card for speaker with photo | name | panel job | affiliation | twitter | github
  // Only the speaker name is mandatory but you should check that there is a SURNAME_NAME.jpg
  // photo in the img/speakers folder
  // For the other fields, it only appears if the value is defined in the _data/speakers.csv
  if (!speaker.Name || speaker.Name === "") {
    return "";
  }

  const speakerUrl = getUrlForSpeaker(speaker);

  return `
    <div>
      <a style="color:#05323F" href="${speakerUrl}">
        <img src=${getImageAssetPathForSpeaker(speaker)} />

        <h3>${speaker.Name}</h3>
        ${speaker.Job ? `<h4>${speaker.Job}</h4>` : ""}
        ${speaker.Affiliation ? `<h6>${speaker.Affiliation}</h6>` : ""}
      </a>
      ${speaker.Twitter ? `<a target="_blank" href="${speaker.Twitter}"><i class="fa fa-twitter fa-2x"></i></a>` : ""}
      ${speaker.GitHub ? `<a target="_blank" href="${speaker.GitHub}"><i class="fa fa-github fa-2x"></i></a>` : ""}
    </div>
  `;
}

function displayPanel(panelName) {
  // Generate divs that contain all the speakers that are in the given panel
  const speakers = getPanelSpeakersForPanelName(panelName);
  return `${speakers.map(formatSpeakerDiv).join("")}`;
}

</script>
</html>


The OSR has always been a place to learn and share experiences.
This year we are centering these experiences around themes which are undergoing rapid change in our discipline. 

For each panel discussion session, we are looking for 1-2 self-nominated panelists. 
**If you are interested in joining as a panelist and would like to self-nominate, please self-register <a href="https://forms.office.com/r/pBYUbr5bEg" target="_blank">here</a>!** <br>

## Topic 1: Open Science - Who pays the bill?
#### <a href="https://www.crowdcast.io/c/panel-1-bills" target="_blank"> Join on Crowdcast</a> 
When: 9:00 GMT+9 | June 24, 2024 (Monday) <br/>
<br/>
<div>
<img src="../img/Panel1-speakers.png" alt = "panel1" width="100%" style="margin:10px 10px;">
</div>
With a growing interest in Open Science, questions arise regarding who is paying for what and what 'inclusive' means. If Open Access publication comes with high fees, one can ask whether this shift in payment responsibility, from the reader to the author, is excluding more people than it includes. Related to this is the question of the relationship between Open Access and Impact Factors and how much this affects researchers from different backgrounds and at different stages of their careers. There are also invisible costs to Open Science, such as platforms for sharing preprints, code, and data. Who develops, maintains, and hosts these platforms, and why? These are examples of the questions that will be addressed during this panel discussion. Experts with diverse backgrounds will share their experiences and thoughts. An open discussion on these matters will foster critical inquiry into the ideal form that Open Science should take.   
<br><br>

At the end of the panel discussion, the audience members will be able to:
  1. Giving insight into who pays in for what (neuro-)science and who does that affects most.
  2. Stimulate critical thinking on how to make Open Science inclusive in terms of costs.
<br/>

<html>
<div class="panel-speakers" id="panel1"></div>

<script>
document.getElementById("open-science-panel").innerHTML = displayPanel("Open Science");
</script>
</html>

## Topic 2: Getting Started in Open Science
#### <a href="https://www.crowdcast.io/c/panel-2-start" target="_blank">Join on Crowdcast</a> 
When: 9:00 GMT+9 | June 25, 2024 (Tuesday) <br/>
<p>
<img src="../img/Panel2-speakers.png" alt = "panel2" width="100%" style="margin:10px 10px;">
</p>
<br/>
There is rapid change occurring in and shaping the landscape of the scientific community that is caused by the open science movement. The panellists will dive into deconstructing and defining open access; open data, materials, and code; as well as touch on facilitating reproducible analyses, preregistration and registered reports such as in PrePrints, easy replication of research methods, inclusive of teaching open science practices. An open discussion on these matters will foster critical inquiry into the ideal form that Open Science should take, with recommendations of best practices in Open Science. 
<br><br>

At the end of the panel discussion, the audience members will be able to:
  1. Giving insight in what are the best practices in Open Science.
  2. Stimulate critical thinking on how to make Open Science inclusive in terms of participants from various geographical locations, gender, race and disabilities.
<br/>
<html>
<div class="panel-speakers" id="panel2"></div>

<script>
document.getElementById("open-publishing-panel").innerHTML = displayPanel("Open Publishing");
</script>
</html>

## Topic 3: Many A Little Makes A Mickle: Crowdsourcing for brain mapping
#### <a href="https://www.crowdcast.io/c/panel-3-crowdsource" target="_blank"> Join on Crowdcast </a> 
When: 13:30 GMT+9 | June 25, 2024 (Tuesday) <br/>
<p>
<img src="../img/Panel3-speakers.png" alt = "panel3" width="100%" style="margin:10px 10px;">
</p>
<br/>
Crowdsourcing e.g., multi-site collaboration and citizen science, is rising as a new research paradigm. By harnessing the power of crowdsourcing, we can leverage the diverse expertise and perspectives of a global community to accelerate advancements in brain mapping. This collaborative approach not only facilitates the sharing of data and resources but also promotes innovation and efficiency in tackling the complexities of understanding the brain. With the following examples of the questions that will be addressed during this panel discussion, experts with diverse backgrounds will share their experiences and thoughts.
<br><br>

Specific topics of discussion include:
  - How does crowdsourcing work in brain mapping research? 
  - What are the ethical considerations unique to crowdsourcing projects? 
<br><br>

At the end of the panel discussion, the audience members will be able to:
  1. Get insights into how crowdsourcing and open science work and identify optimal crowdsourcing models for brain mapping research.
  2. Develop a nuanced understanding of ethical considerations unique to crowdsourcing neuroscience projects.
<br>
<html>
<div class="panel-speakers" id="panel5"></div>

<script>
document.getElementById("social-bias-panel").innerHTML = displayPanel("Social Bias");
</script>
</html>

## Topic 4: The changing face of Open Science
#### <a href="https://www.crowdcast.io/c/panel-4-changing" target="_blank"> Join on Crowdcast </a> 
When: 11:15 GMT+9 | June 26, 2024 (Wednesday) <br/>
<p>
<img src="../img/Panel4-speakers.png" alt = "panel4" width="100%" style="margin:10px 10px;">
</p>
<br/>
There has been a dramatic shift in the uptake of open science practices in the past thirty years. This has led to considerable change in how we collect, analyze and distribute data, how we publish and disseminate findings, and how we recruit staff and seek employment. How we do science has changed - and so understanding what has happened, why, and where things may yet change is of key importance to researchers from all fields. Attendees will find out about the drivers behind many of these changes - whether they have lived up to expectations, and where any gaps remain.
<br><br>

At the end of the panel discussion, the audience members will be able to:
  1. Consider the major initiatives of open science and find out how these developments can be used to improve your workflows.
  2. Develop a deep understanding of how open science fits within the broader publishing and funding landscapes.
<br/>
<html>
<div class="panel-speakers" id="panel3"></div>

<script>
document.getElementById("open-code-panel").innerHTML = displayPanel("Open Code");
</script>
</html>

## Topic 5: Open Science in Asia/Korea
#### <a href="https://www.crowdcast.io/c/panel-5-asia" target="_blank">Join on Crowdcast</a> 
When: 9:00 GMT+9 | June 27, 2024 (Thursday) <br/>
<p>
<img src="../img/Panel5-speakers.png" alt = "panel5" width="100%" style="margin:10px 10px;">
</p>
<br/>
Although Open Science has been well-recognized by the neuroimaging field as a crucial step towards better scientific practices that facilitate reproducibility and reliability, the progress has mainly taken place in the Western world. Asia, or Korea specifically, is relatively new to the practice and the idea and has encountered unique challenges. With the annual meeting of OHBM being held in an Asian, non-English speaking country, this meeting provides a unique opportunity for local researchers who are interested in Open Science to share their experiences and challenges they face in their countries. This discussion will foster the development of Open Science through international collaboration and advance the Open Science practice to being more inclusive globally.
<br><br>

Specific topics of discussion include:
  - What is stopping people from practicing Open Science?
  - What is stopping institutions and governments to support Open Science?
  - How do you think the community could help?
<br><br>

At the end of the panel discussion, the audience members will be able to:
  1. Understanding the current Open Science in Asia/Korea.
  2. Learn about the unique challenges Asian/Korean Open Science researchers are facing.
  3. Initiate discussion for possible solutions and support.
<br/>
<html>
<div class="panel-speakers" id="panel4"></div>

<script>
document.getElementById("statistical-perspectives-panel").innerHTML = displayPanel("Statistical Perspectives");
</script>
</html>
