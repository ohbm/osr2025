---
layout: page
title: Panels and Round Tables
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

This year, we are featuring 1 round tables and 2 panels.

<!-- For each panel discussion session, we are looking for 1-2 self-nominated panelists. 
Registration will be open soon! -->
<!-- **If you are interested in joining as a panelist and would like to self-nominate, please self-register <a href="https://forms.office.com/r/pBYUbr5bEg" target="_blank">here</a>!** <br> -->

## OSR Round Table: Open Science Room Opening ft. BIDS annual updates
#### <a href="https://www.crowdcast.io/c/osr-round-table-1" target="_blank"> Join on Crowdcast</a> 
When: 8:00 GMT+10 | June 25, 2025 (Wednesday) <br/>
Moderators & Speakers: Ju-Chi Yu (OSR Chair), James Kent (OSR Chair-Elect), <br/>
Gabriel Pelletier (TOSI), Russ Poldrack (OpenNeuro), Vijay Iyer (MathWorks), <br/> 
Kim Ray (the BIDS Team), Eric Earl (the BIDS team)
<br/>
<!-- <div>
<img src="../img/Panel1-speakers.png" alt = "panel1" width="100%" style="margin:10px 10px;">
</div> -->
With a growing interest in Open Science in the OHBM community, this session will introduce Open Science Room (OSR) events during OHBM 2025 with the current progress of the Open Science Special Interest Group (OSSIG) and the working group of an Open Science Tool that is widely used by the OHBM community; this year, we are featuring the Brain Imaging Data Structure (BIDS). This session aims to bring people’s attention to the Open Science initiative at OHBM. This opening session helps us bring awareness of our progress and expand the Open Science community beyond the North American and European networks. Such expansion will lead to a more diverse community and make Open Science practices more inclusive. We will address the current progress of OSR and OSSIG and welcome feedback from the community for future planning. By partnering with the BIDS team, we aim to reach out to the broader users and developers community of Open Science. A Q&A session at the end will foster interactive discussions with the broad Open Science community at OHBM. 
<br><br>

This round table will:
  1. Provide updates and awareness of the Open Science Room and the Open Science Special Interest Group
  2. Provide annual updates on the development of the Brain Imaging Data Structure (BIDS) tools
<br/>

<!-- <html>
<div class="panel-speakers" id="panel1"></div>
<script>
document.getElementById("open-science-panel").innerHTML = displayPanel("Open Science");
</script>
</html> -->

## OSR Cross-Societies Panel: The role of scientific communities, pt. 1: open tools for open (neuro)imaging.
<!-- #### <a href="https://www.crowdcast.io/c/panel-2-start" target="_blank">Join on Crowdcast</a>  -->
When: 8:00 GMT+10 | June 26, 2025 (Thursday) <br/>
Moderators: Stefano Moia (OSSIG), Cristian Montalba (MRITogether)
Speakers: Udunna Anazodo (CAMERA), Kim Ray (BRIDGE), Jarrod Millman (Scientific Python), Dominique Makowsk (Neurokit)

<!-- <p>
<img src="../img/Panel2-speakers.png" alt = "panel2" width="100%" style="margin:10px 10px;">
</p> -->
<br/>
While science has never really been a solo endeavour, we are increasingly observing the inception of scientific communities of any kind and size to address emerging scientific problems with a new perspective, that of international collaborative spirit.
In this panel discussion, co-organized by three Open Science communities across three societies (the OSSIG from OHBM, the Reproducible Research Study Group of ISMRM, and the organizers of MRITogether by ESMRMB), we will continue exploring this exciting approach to doing science, looking at the outcome and deliverables of scientific communities in the field of (neuro)imaging, exploring synergies and the exchange with more traditional forms of academic organization. 
<br><br>

At this panel discussion, we wil:
  1. Introduce different scientific communities with open science interest groups.
  2. Provide specific examples of international scientific communities' achievements and new instruments for neuroimaging and open science.
  3. Provide best practices for inclusive, international collaboration with flat hierarchies and democratic decision making.

<br/>

<!-- <html>
<div class="panel-speakers" id="panel2"></div> -->
<!-- <script>
document.getElementById("open-publishing-panel").innerHTML = displayPanel("Open Publishing");
</script>
</html> -->

## OSR Panel: Harnessing AI and Biological Systems for Advancing Neuroimaging and Biomedical Research
<!-- #### <a href="https://www.crowdcast.io/c/panel-3-crowdsource" target="_blank"> Join on Crowdcast </a>  -->
When: 13:00 GMT+10 | June 27, 2025 (Friday) <br/>
Moderators: Newsha Dehestani, Bruno Hebling Vieira
Speakers: Zhang Yich, Fourough Habibolahi, Satrajit Ghosh
<!-- <p>
<img src="../img/Panel3-speakers.png" alt = "panel3" width="100%" style="margin:10px 10px;">
</p> -->
<br/>
As AI continues to advance, its integration into neuroimaging and biomedical research brings both immense potential and complex challenges. We will examine the role of open science principles in AI-based brain decoding projects, the ethical considerations of AI in biomedical research, and how biological systems can inspire machine learning models. The session will also highlight emerging standards for AI-readiness in biomedical data and the ethical implications of AI in clinical practice. Experts with diverse backgrounds in AI, neuroimaging, and biological systems will share their insights and experiences, fostering an open discussion that encourages critical thinking about the future of AI in neuroimaging. By exploring these timely issues, the symposium will provide valuable knowledge on the best practices for responsible AI use and how biological systems can enhance machine learning efficiency. The goal is to promote deeper understanding and encourage the development of AI methods that are both scientifically rigorous and ethically sound, benefiting researchers, clinicians, and AI practitioners alike.
<br><br>

This panel discussion will:
  1. Provide insights into the ethical considerations and standards for AI applications in neuroimaging and biomedical research, including AI-readiness of biomedical data and explainable AI (XAI).
  2. Stimulate critical thinking on how open science principles, including reproducibility, can be implemented inclusively in AI-driven neuroimaging research, addressing both financial and accessibility challenges.
  3. Explore the role of biological neural networks in enhancing the efficiency of machine learning models, encouraging discussions on how biological systems can inspire advancements in AI and neuroimaging applications.
<br>

<!-- <html>
<div class="panel-speakers" id="panel5"></div> -->
<!-- <script>
document.getElementById("social-bias-panel").innerHTML = displayPanel("Social Bias");
</script>
</html> -->