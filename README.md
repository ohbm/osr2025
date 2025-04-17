## Welcome!

This is the GitHub repository for the OHBM Open Science Room (OSR).

This repository hosts the code for [the OSR2024 website](https://ohbm.github.io/osr2024).

Below we provide basic info and links to more information. 

### Who are we?

We are part of the <a href="https://ossig.netlify.com/">Open Science Special Interest Group</a>(OSSIG) of the <a href="https://www.humanbrainmapping.org/i4a/pages/index.cfm?pageid=3267&pageid=1">Organization for Human Brain Mapping</a>.

### What are we doing?

We are organizing, among other events, the Open Science Room at the <a href="https://www.humanbrainmapping.org/i4a/pages/index.cfm?pageid=4114" target="_blank">2024 meeting of the OHBM</a>.

### Get involved

All information is available on <a href="https://ohbm.github.io/osr2024" target="_blank">our website</a>.

### Contact us

Feel free to <a href="https://ohbm.github.io/osr2024/contact/" target="_blank">reach out to us</a>!


---

### Credit
The [OSR website](https://ohbm.github.io/osr2023) was built using the [Beautiful Jekyll](https://deanattali.com/beautiful-jekyll/) theme by [Dean Attali](https://deanattali.com/).


#### Instructions for building website (these must be run prior to uploading onto GH)
+ Check the speaker/volunteer CSV files are in place (in _data/speakers, _data/volunteers)
Wipe the built directories if they already exist, and re-build: 
`rm -r _speakers _volunteers; bundle exec jekyll pagemaster speakers volunteers`
Commit the new directories and push the site. This must be done every time the CSV files are changed. 

+ If `bundle exect` error out, do the following things:

    1. Create Gemfile
    2. Follow the errors and add all required dependencies
    3. Run `bundel install`



