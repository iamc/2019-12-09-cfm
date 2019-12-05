---
layout: workshop      # DON'T CHANGE THIS.
venue: "Centro de Física de Materiales (CSIC-UPV/EHU)"        # brief name of host site without address (e.g., "Euphoric State University")
address: "CFM Computer Room SSB-008A, basement floor"      # full street address of workshop (e.g., "Room A, 123 Forth Street, Blimingen, Euphoria")
country: "ES"      # lowercase two-letter ISO country code such as "fr" (see https://en.wikipedia.org/wiki/ISO_3166-1#Current_codes)
language: "EN"     # lowercase two-letter ISO language code such as "fr" (see https://en.wikipedia.org/wiki/List_of_ISO_639-1_codes)
latitude: "43.305667"     # decimal latitude of workshop venue (use https://www.latlong.net/)
longitude: "-2.009502"    # decimal longitude of the workshop venue (use https://www.latlong.net)
humandate: "December 16 and 18th, 2019, and January 14, 15 and 16th, 2020,  9:00h - 13:00h (separated morning sessions)"    # human-readable dates for the workshop (e.g., "Feb 17-18, 2020")
humantime: "9:00h - 13:00h (separated morning sessions)"    # human-readable times for the workshop (e.g., "9:00 am - 4:30 pm")
startdate: 2019-12-16      # machine-readable start date for the workshop in YYYY-MM-DD format like 2015-01-01
enddate: 2020-01-16        # machine-readable end date for the workshop in YYYY-MM-DD format like 2015-01-02
instructor: ["Iñigo Aldazabal", "Sonia Olaechea", "Ainhoa Oliden", "Tineke van den Berg"]# boxed, comma-separated list of instructors' names as strings, like ["Kay McNulty", "Betty Jennings", "Betty Snyder"]
helper: [ "Unai Aseguinolaza", "Abel Carreras", "Mikel Iraola", "Alvaro Nodar", "Xiang Xu"]     # boxed, comma-separated list of helpers' names, like ["Marlyn Wescoff", "Fran Bilas", "Ruth Lichterman"]
email: ["inigo.aldazabalm@ehu.eus"]    # boxed, comma-separated list of contact email addresses for the host, lead instructor, or whoever else is handling questions, like ["marlyn.wescoff@example.org", "fran.bilas@example.org", "ruth.lichterman@example.org"], collaborative_notes:             # optional: URL for the workshop collaborative notes, e.g. an Etherpad or Google Docs document
eventbrite:           # optional: alphanumeric key for Eventbrite registration, e.g., "1234567890AB" (if Eventbrite is being used)
---

{% comment %} See instructions in the comments below for how to edit specific sections of this workshop template. {% endcomment %}

{% comment %}
HEADER

Edit the values in the block above to be appropriate for your workshop.
If the value is not 'true', 'false', 'null', or a number, please use
double quotation marks around the value, unless specified otherwise.
And run 'make workshop-check' *before* committing to make sure that changes are good.
{% endcomment %}

<h4 id="general">Contents</h4>
<p><small>
 <ul>
  <li><a href="#general">General Information</a></li>
  <li><a href="#registration">Registration</a></li>
  <li><a href="#schedule">Schedule</a></li>
  <li><a href="#syllabus">Syllabus</a></li>
  <li><a href="#setup">Software Setup Instructions</a></li>
</ul>
</small></p>

{% comment %}
For a workshop please delete the following block
{% endcomment %}

{% comment %}
Check DC curriculum
{% endcomment %}

{% if site.carpentry == "dc" or site.carpentry == "dc" %}
{% unless site.curriculum == "dc-ecology" or site.curriculum == "dc-genomics" or site.curriculum == "dc-socsci" or site.curriculum == "dc-geospatial" %}
<div class="alert alert-warning">
It looks like you are setting up a website for a Data Carpentry curriculum but you haven't specified the curriculum type in the <code>_config.yml</code> file (current value in <code>_config.yml</code>: "<strong>{{ site.curriculum }}</strong>", possible values: <code>dc-ecology</code>, <code>dc-genomics</code>, <code>dc-socsci</code>, or <code>dc-geospatial</code>). After editing this file, you need to run <code>make serve</code> again to see the changes reflected.
</div>
{% endunless %}
{% endif %}

{% comment %}
EVENTBRITE

This block includes the Eventbrite registration widget if
'eventbrite' has been set in the header.  You can delete it if you
are not using Eventbrite, or leave it in, since it will not be
displayed if the 'eventbrite' field in the header is not set.
{% endcomment %}
{% if page.eventbrite %}
<iframe
  src="https://www.eventbrite.com/tickets-external?eid={{page.eventbrite}}&ref=etckt"
  frameborder="0"
  width="100%"
  height="280px"
  scrolling="auto">
</iframe>
{% endif %}


<h2 id="general">General Information</h2>

{% comment %}
INTRODUCTION

Edit the general explanatory paragraph below if you want to change
the pitch.
{% endcomment %}
{% if site.carpentry == "swc" %}
{% include swc/intro.html %}
{% elsif site.carpentry == "dc" %}
{% include dc/intro.html %}
{% elsif site.carpentry == "lc" %}
{% include lc/intro.html %}
{% endif %}

{% comment %}
AUDIENCE

Explain who your audience is.  (In particular, tell readers if the
workshop is only open to people from a particular institution.
{% endcomment %}
{% if site.carpentry == "swc" %}
{% include swc/who.html %}
{% elsif site.carpentry == "dc" %}
{% include dc/who.html %}
{% elsif site.carpentry == "lc" %}
{% include lc/who.html %}
{% endif %}

{% comment %}
LOCATION

This block displays the address and links to maps showing directions
if the latitude and longitude of the workshop have been set.  You
can use https://itouchmap.com/latlong.html to find the lat/long of an
address.
{% endcomment %}
{% if page.latitude and page.longitude %}
<p id="where">
  <strong>Where:</strong>
  {{page.address}}.
  Get directions with
  <a href="//www.openstreetmap.org/?mlat={{page.latitude}}&mlon={{page.longitude}}&zoom=16">OpenStreetMap</a>
  or
  <a href="//maps.google.com/maps?q={{page.latitude}},{{page.longitude}}">Google Maps</a>.
</p>
{% endif %}

{% comment %}
DATE

This block displays the date and links to Google Calendar.
{% endcomment %}
{% if page.humandate %}
<p id="when">
  <strong>When:</strong>
  {{page.humandate}}.
<!--
  {% include workshop_calendar.html %}
-->
</p>
{% endif %}


{% comment %}
ACCESSIBILITY

Modify the block below if there are any barriers to accessibility or
special instructions.
{% endcomment %}
<p id="accessibility">
  <strong>Accessibility:</strong> We are committed to making this workshop
  accessible to everybody.
  The workshop organizers have checked that:
</p>
<ul>
  <li>The room is wheelchair / scooter accessible.</li>
  <li>Accessible restrooms are available.</li>
</ul>
<p>
  Materials will be provided in advance of the workshop and
  large-print handouts are available if needed by notifying the
  organizers in advance.  If we can help making learning easier for
  you (e.g. sign-language interpreters, lactation facilities) please
  get in touch (using contact details below) and we will
  attempt to provide them.
</p>

{% comment %}
SPECIAL REQUIREMENTS

Modify the block below if there are any special requirements.
{% endcomment %}
<div class="alert alert-warning">
<p id="requirements">
  <strong>Requirements:</strong> Participants are <strong>strongly encouraged</strong> to bring their own laptop with a
  Mac, Linux, or Windows operating system (not a tablet, Chromebook, etc.) with a few specific software packages installed (listed
  <a href="#setup">below</a>). In case you can't bring one, the Computer Room computers will be setup and available for the workshop.
</p>
<p id="code-of-conduct">
  <br>  Participants are also required to abide by
  {% if page.carpentry == "swc" %}
  Software Carpentry's
  {% elsif page.carpentry == "dc" %}
  Data Carpentry's
  {% elsif page.carpentry == "lc" %}
  Library Carpentry's
  {% endif %}
  <a href="{{site.swc_site}}/conduct.html">Code of Conduct</a>.
</p>
</div>

{% comment %}
CONTACT EMAIL ADDRESS

Display the contact email address set in the configuration file.
{% endcomment %}
<p id="contact">
  <strong>Contact</strong>:
  Please email
  {% if page.email %}
  {% for email in page.email %}
  {% if forloop.last and page.email.size > 1 %}
  or
  {% else %}
  {% unless forloop.first %}
  ,
  {% endunless %}
  {% endif %}
  <a href='mailto:{{email}}'>{{email}}</a>
  {% endfor %}
  {% else %}
  to-be-announced
  {% endif %}
  for more information.
</p>

<hr/>

{% comment %} 
 REGITRATION 
 Google form link https://forms.gle/jq3gfAzBptaG4ynb8
{% endcomment %}
<h2 id="registration">Registration</h2>
<p>Assistance is limited to 20 people, and CFM/DIPC staff will have priority. Appart from this seats will be assigned in a first-come fist-served basis.</p>

<div style="display: block;" class="classictemplate template">
<style type="text/css">
  #groupsio_embed_signup input {border:1px solid #999; -webkit-appearance:none;}
  #groupsio_embed_signup label {display:block; font-size:16px; padding-bottom:10px; font-weight:bold;}
  #groupsio_embed_signup .email {display:block; padding:8px 0; margin:0 4% 10px 0; text-indent:5px; width:58%; min-width:130px;}
  #groupsio_embed_signup {
    background:#fff; clear:left; font:14px Helvetica,Arial,sans-serif;
  }
  #groupsio_embed_signup .button {
      width:25%; margin:0 0 10px 0; min-width:90px;
      background-image: linear-gradient(to bottom,#337ab7 0,#265a88 100%);
      background-repeat: repeat-x;
      border-color: #245580;
      text-shadow: 0 -1px 0 rgba(0,0,0,.2);
      box-shadow: inset 0 1px 0 rgba(255,255,255,.15),0 1px 1px rgba(0,0,0,.075);
      padding: 5px 10px;
      font-size: 12px;
      line-height: 1.5;
      border-radius: 3px;
      color: #fff;
      background-color: #337ab7;
      display: inline-block;
      margin-bottom: 0;
      font-weight: 400;
      text-align: center;
      white-space: nowrap;
      vertical-align: middle;
    }
</style>
<div id="groupsio_embed_signup">
<!--
<form action="https://groups.io/g/lund-SC-workshop/signup?u=2154170982873630030" method="post" id="groupsio-embedded-subscribe-form" name="groupsio-embedded-subscribe-form" target="_blank">
-->
<form target="_blank" action="https://forms.gle/dpYyRQJ2UpycSzQ8A" method="GET">
    <div id="groupsio_embed_signup_scroll">
    <div style="position: absolute; left: -5000px;" aria-hidden="true"><input name="b_2154170982873630030" tabindex="-1" value="" type="text"></div>
    <div id="templatearchives"></div>
    <input value="Register here" name="subscribe" id="groupsio-embedded-subscribe" class="button" type="submit"/>
  </div>
</form>
</div>
</div>


<hr/>

{% comment %} 
SURVEYS - DO NOT EDIT SURVEY LINKS 
{% endcomment %}
<h2 id="surveys">Surveys</h2>
<p>Please be sure to complete these surveys before and after the workshop.</p>
<p><a href="{{ site.pre_survey }}{{ site.github.project_title }}">Pre-workshop Survey</a></p>
<p><a href="{{ site.post_survey }}{{ site.github.project_title }}">Post-workshop Survey</a></p>

<hr/>


{% comment %}
SCHEDULE

Show the workshop's schedule.  Edit the items and times in the table
to match your plans.  You may also want to change 'Day 1' and 'Day
2' to be actual dates or days of the week.
{% endcomment %}
<h2 id="schedule">Schedule</h2>

{% if site.carpentry == "swc" %}
{% include swc/schedule.html %}
{% elsif site.carpentry == "dc" %}
{% include dc/schedule.html %}
{% elsif site.carpentry == "lc" %}
{% include lc/schedule.html %}
{% endif %}

{% comment %}
Collaborative Notes

If you want to use an Etherpad, go to

http://pad.carpentries.org/YYYY-MM-DD-site

where 'YYYY-MM-DD-site' is the identifier for your workshop,
e.g., '2015-06-10-esu'.
{% endcomment %}
{% if page.collaborative_notes %}
<p id="collaborative_notes">
  We will use this <a href="{{page.collaborative_notes}}">collaborative document</a> for chatting, taking notes, and sharing URLs and bits of code.
</p>
{% endif %}

<hr/>

{% comment %}
SYLLABUS

Show what topics will be covered.

1. If your workshop is R rather than Python, remove the comment
around that section and put a comment around the Python section.
2. Some workshops will delete SQL.
3. Please make sure the list of topics is synchronized with what you
intend to teach.
4. You may need to move the div's with class="col-md-6" around inside
the div's with class="row" to balance the multi-column layout.

This is one of the places where people frequently make mistakes, so
please preview your site before committing, and make sure to run
'tools/check' as well.
{% endcomment %}
<h2 id="syllabus">Syllabus</h2>

{% if site.carpentry == "swc" %}
{% include swc/syllabus.html %}
{% elsif site.carpentry == "dc" %}
{% include dc/syllabus.html %}
{% elsif site.carpentry == "lc" %}
{% include lc/syllabus.html %}
{% endif %}

<hr/>

{% comment %}
SETUP

Delete irrelevant sections from the setup instructions.  Each
section is inside a 'div' without any classes to make the beginning
and end easier to find.

This is the other place where people frequently make mistakes, so
please preview your site before committing, and make sure to run
'tools/check' as well.
{% endcomment %}

<h2 id="setup">Setup</h2>

<p>
  To participate in a
  {% if site.carpentry == "swc" %}
  Software Carpentry
  {% elsif site.carpentry == "dc" %}
  Data Carpentry
  {% elsif site.carpentry == "lc" %}
  Library Carpentry
  {% endif %}
  workshop,
  you will need access to the software described below.
  In addition, you will need an up-to-date web browser.
</p>
<p>
  We maintain a list of common issues that occur during installation as a reference for instructors
  that may be useful on the
  <a href = "{{site.swc_github}}/workshop-template/wiki/Configuration-Problems-and-Solutions">Configuration Problems and Solutions wiki page</a>.
</p>

{% if site.carpentry == "swc" %}
{% include swc/setup.html %}
{% elsif site.carpentry == "dc" %}
{% include dc/setup.html %}
{% elsif site.carpentry == "lc" %}
{% include lc/setup.html %}
{% endif %}
