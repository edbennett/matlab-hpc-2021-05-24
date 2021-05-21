---
layout: workshop      # DON'T CHANGE THIS.
carpentry: "sa2c"    # what kind of Carpentry (must be either "lc", "dc", "swc", "sa2c" or "sa2c_mpi")
venue: "High Performance Computing with MATLAB"        # brief name of host site without address (e.g., "Euphoric State University")
address: "Online"      # full street address of workshop (e.g., "Room A, 123 Forth Street, Blimingen, Euphoria")
country: "United Kingdom"      # lowercase two-letter ISO country code such as "fr" (see https://en.wikipedia.org/wiki/ISO_3166-1)
language: "English"     # lowercase two-letter ISO language code such as "fr" (see https://en.wikipedia.org/wiki/ISO_639-1)
latlng: "51.619229,-3.878739"       # decimal latitude and longitude of workshop venue (e.g., "41.7901128,-87.6007318" - use https://www.latlong.net/)
humandate: "May 24-27, 2021"    # human-readable dates for the workshop (e.g., "Feb 17-18, 2020")
humantime: "1:00pm - 4:30pm"    # human-readable times for the workshop (e.g., "9:00 am - 4:30 pm")
startdate: 2021-05-24      # machine-readable start date for the workshop in YYYY-MM-DD format like 2015-01-01
enddate: 2021-05-27        # machine-readable end date for the workshop in YYYY-MM-DD format like 2015-01-02
scw_project: "scw1389"  # project code for the SCW training project for this event
instructor: ["Ben Thorpe", "Vladimir Khodygo"] # boxed, comma-separated list of instructors' names as strings, like ["Kay McNulty", "Betty Jennings", "Betty Snyder"]
helper: ["Ed Bennett", "Michele Mesiti"]     # boxed, comma-separated list of helpers' names, like ["Marlyn Wescoff", "Fran Bilas", "Ruth Lichterman"]
email: ["e.j.bennett@swansea.ac.uk"]    # boxed, comma-separated list of contact email addresses for the host, lead instructor, or whoever else is handling questions, like ["marlyn.wescoff@example.org", "fran.bilas@example.org", "ruth.lichterman@example.org"]
collaborative_notes:             # optional: URL for the workshop collaborative notes, e.g. an Etherpad or Google Docs document
eventbrite:           # optional: alphanumeric key for Eventbrite registration, e.g., "1234567890AB" (if Eventbrite is being used)
recon_channel:        # optional: url for specific recon channel to join
---

{% comment %} See instructions in the comments below for how to edit specific sections of this workshop template. {% endcomment %}

{% comment %}
  HEADER

  Edit the values in the block above to be appropriate for your workshop.
  If the value is not 'true', 'false', 'null', or a number, please use
  double quotation marks around the value, unless specified otherwise.
  And run 'make workshop-check' *before* committing to make sure that changes are good.
{% endcomment %}

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
{% if page.carpentry == "swc" %}
  {% include sc/intro.html %}
{% elsif page.carpentry == "dc" %}
  {% include dc/intro.html %}
{% elsif page.carpentry == "lc" %}
  {% include lc/intro.html %}
{% elsif page.carpentry == "sa2c" %}
  {% include sa2c/intro.html %}
{% elsif page.carpentry == "sa2c_mpi" %}
  {% include sa2c_mpi/intro.html %}
{% endif %}

{% comment %}
  AUDIENCE

  Explain who your audience is.  (In particular, tell readers if the
  workshop is only open to people from a particular institution.
{% endcomment %}
{% if page.carpentry == "swc" %}
  {% include sc/who.html %}
{% elsif page.carpentry == "dc" %}
  {% include dc/who.html %}
{% elsif page.carpentry == "lc" %}
  {% include lc/who.html %}
{% elsif page.carpentry == "sa2c" %}
  {% include sa2c/who.html %}
{% elsif page.carpentry == "sa2c_mpi" %}
  {% include sa2c_mpi/who.html %}
{% endif %}

{% comment %}
  LOCATION

  This block displays the address and links to maps showing directions
  if the latitude and longitude of the workshop have been set.  You
  can use https://itouchmap.com/latlong.html to find the lat/long of an
  address.
{% endcomment %}
{% if page.latlng %}
<p id="where">
  <strong>Where:</strong>
  {{page.address}}.
  Get directions with
  <a href="//www.openstreetmap.org/?mlat={{page.latlng | replace:',','&mlon='}}&zoom=16">OpenStreetMap</a>
  or
  <a href="//maps.google.com/maps?q={{page.latlng}}">Google Maps</a>.
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
  {% include workshop_calendar.html %}
</p>
{% endif %}

{% comment %}
  SPECIAL REQUIREMENTS

  Modify the block below if there are any special requirements.
{% endcomment %}
<p id="requirements">
  <strong>Requirements:</strong> You will need a computer with macOS, Linux, or
  Windows operating system (not a tablet, Chromebook, etc.) that you have
  administrative privileges on. As this is a course on improving the performance
  of MATLAB code, you will need some experience of programming in MATLAB. You
  will also need some familiarity with accessing high-performance computing
  machines using the command line, and using the Slurm job scheduler&mdash;if
  you haven't done these before, we'd recommend reading through the <a
  href="https://supercomputingwales.github.io/SCW-tutorial">Introduction to
  High-Performance Computing with Supercomputing Wales</a> before getting
  started with this material. For the hackathon portion of the event, you will
  be working on a piece of your own research software that you want to improve
  the performance of. You are also required to abide by
  {% if page.carpentry == "swc" %}
  Software Carpentry's
  {% elsif page.carpentry == "dc" %}
  Data Carpentry's
  {% elsif page.carpentry == "lc" %}
  Library Carpentry's
  {% else %}
  The Carpentries'
  {% endif %}
  <a href="{{site.swc_site}}/conduct.html">Code of Conduct</a>.
</p>

{% comment %}
  ACCESSIBILITY

  Modify the block below if there are any barriers to accessibility or
  special instructions.
{% endcomment %}
<p id="accessibility">
  <strong>Accessibility:</strong> We are committed to making this workshop
  accessible to everybody.
  Materials will be provided in advance of the workshop. 
  If we can help making learning easier for you please
  get in touch (using contact details below) and we will
  attempt to provide additional support.
</p>

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
 SURVEYS - DO NOT EDIT SURVEY LINKS 
{% endcomment %}
{% if site.carpenty == "swc" or site.carpentry == "dc" or site.carpentry == "lc" %}
 <h2 id="surveys">Surveys</h2>
{% endif %}
<p>Please be sure to complete these surveys before and after the workshop.</p>
{% if site.carpentry == "swc" %} 
<p><a href="{{ site.swc_pre_survey }}{{ site.github.project_title }}">Pre-workshop Survey</a></p>
<p><a href="{{ site.swc_post_survey }}{{ site.github.project_title }}">Post-workshop Survey</a></p>
{% elsif site.carpentry == "dc" %}
<p><a href="{{ site.dc_pre_survey }}{{ site.github.project_title }}">Pre-workshop Survey</a></p>
<p><a href="{{ site.dc_post_survey }}{{ site.github.project_title }}">Post-workshop Survey</a></p>
{% elsif site.carpentry == "lc" %}
<p><a href="{{ site.lc_pre_survey }}{{ site.github.project_title }}">Pre-workshop Survey</a></p>
<p><a href="{{ site.lc_post_survey }}{{ site.github.project_title }}">Post-workshop Survey</a></p>
{% endif %}

<hr/>


{% comment %}
  SCHEDULE

  Show the workshop's schedule.  Edit the items and times in the table
  to match your plans.  You may also want to change 'Day 1' and 'Day
  2' to be actual dates or days of the week.
{% endcomment %}
<h2 id="schedule">Schedule</h2>

{% if page.carpentry == "swc" %}
  {% include sc/schedule.html %}
{% elsif page.carpentry == "dc" %}
  {% include dc/schedule.html %}
{% elsif page.carpentry == "lc" %}
  {% include lc/schedule.html %}
{% elsif page.carpentry == "sa2c" %}
  {% include sa2c/schedule.html %}
{% elsif page.carpentry == "sa2c_mpi" %}
  {% include sa2c_mpi/schedule.html %}
{% endif %}

{% comment %}
  Collaborative Notes

  If you want to use an Etherpad, go to

      http://pad.software-carpentry.org/YYYY-MM-DD-site

  where 'YYYY-MM-DD-site' is the identifier for your workshop,
  e.g., '2015-06-10-esu'.
{% endcomment %}
<p id="collaborative_notes">
  We will use <a href="{% if page.recon_channel %}{{page.recon_channel}}{% else %}https://recon.swansea.ac.uk{% endif %}">ReCoN</a>, the
  Swansea University Research Computing Network, for chatting, taking notes, and sharing URLs and bits of code.
</p>


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
{% if page.carpentry != "sa2c_mpi" %}
<h2 id="syllabus">Syllabus</h2>

{% if page.carpentry == "swc" %}
  {% include sc/syllabus.html %}
{% elsif page.carpentry == "dc" %}
  {% include dc/syllabus.html %}
{% elsif page.carpentry == "lc" %}
  {% include lc/syllabus.html %}
{% elsif page.carpentry == "sa2c" %}
  {% include sa2c/syllabus.html %}
{% endif %}

<hr/>
{% endif %}

<h2 id="setup">Setup</h2>

<div id="matlab"> {% comment %} Start of 'matlab' section. {% endcomment %}
  <h3>MATLAB</h3>
<p>
  To participate in the workshop,
  you will need access to MATLAB software and the Parallel Computing
  Toolbox in MATLAB. You also need to the <strong> Bash Shell</strong>
  to access the supercomputing machine.
  In addition, you will need an up-to-date web browser.
</p>
<p>
  If you do not already have MATLAB installed on your PC, then you 
  can install a student version of MATLAB by following the installation 
  instructions provided at <a href = "https://myuni.swansea.ac.uk/it-services/software-enquiry/"> Install MATLAB</a>.
</p>
<p>
  If you already have MATLAB installed on your PC, then make sure that 
  you have the Parallel Computing Toolbox installed. To check if you 
  have this toolbox installed, type <strong>parpool</strong> at the
  MATLAB's command prompt. 
  If you have paralle computing toolbox installed, then this command 
  will start a parallel pool. Otherwise, you can install the toolbox 
  by using the MATLAB’s installation executable.
</p>
</div> {% comment %} End of 'matlab' section. {% endcomment %}


<div id="shell"> {% comment %} Start of 'shell' section. {% endcomment %}
  <h3>The Bash Shell</h3>

  <p>
    Bash is a commonly-used shell that gives you the power to do simple
    tasks more quickly.
  </p>

  <div class="row">
    <div class="col-md-4">
      <h4 id="shell-windows">Windows</h4>
      <a href="https://www.youtube.com/watch?v=339AEqk9c-8">Video Tutorial</a>
      <ol>
        <li>Download the Git for Windows <a href="https://git-for-windows.github.io/">installer</a>.</li>
        <li>Run the installer and follow the steps below:
          <ol>
            {% comment %} Git 2.18.0 Setup {% endcomment %}
            <li>
                Click on "Next" four times (two times if you've previously
                installed Git).  You don't need to change anything
                in the Information, location, components, and start menu screens.
            </li>
            <li>
                <strong>
                Select “Use the nano editor by default” and click on “Next”.
                </strong>
            </li>
            {% comment %} Adjusting your PATH environment {% endcomment %}
            <li>
                Keep "Use Git from the Windows Command Prompt" selected and click on "Next".
                If you forgot to do this programs that you need for the workshop will not work properly.
                If this happens rerun the installer and select the appropriate option.
            </li>
            {% comment %} Choosing the SSH executable {% endcomment %}
            <li>Click on "Next".</li>
            {% comment %} Configuring the line ending conversions {% endcomment %}
            <li>
                Keep "Checkout Windows-style, commit Unix-style line endings" selected and click on "Next".
            </li>
            {% comment %} Configuring the terminal emulator to use with Git Bash {% endcomment %}
            <li>
              <strong>
                Select "Use Windows' default console window" and click on "Next".
              </strong>
            </li>
            {% comment %} Configuring experimental performance tweaks {% endcomment %}
            <li>Click on "Install".</li>
            {% comment %} Installing {% endcomment %}
            {% comment %} Completing the Git Setup Wizard {% endcomment %}
            <li>Click on "Finish".</li>
          </ol>
        </li>
        <li>
          If your "HOME" environment variable is not set (or you don't know what this is):
          <ol>
            <li>Open command prompt (Open Start Menu then type <code>cmd</code> and press [Enter])</li>
            <li>
              Type the following line into the command prompt window exactly as shown:
              <p><code>setx HOME "%USERPROFILE%"</code></p>
            </li>
            <li>Press [Enter], you should see <code>SUCCESS: Specified value was saved.</code></li>
            <li>Quit command prompt by typing <code>exit</code> then pressing [Enter]</li>
          </ol>
        </li>
      </ol>
      <p>This will provide you with both Git and Bash in the Git Bash program.</p>
    </div>
    <div class="col-md-4">
      <h4 id="shell-macosx">macOS</h4>
      <p>
        The default shell in all versions of macOS is Bash, so no
        need to install anything.  You access Bash from the Terminal
        (found in
        <code>/Applications/Utilities</code>).
        See the Git installation <a href="https://www.youtube.com/watch?v=9LQhwETCdwY ">video tutorial</a>
        for an example on how to open the Terminal.
        You may want to keep
        Terminal in your dock for this workshop.
      </p>
    </div>
    <div class="col-md-4">
      <h4 id="shell-linux">Linux</h4>
      <p>
        The default shell is usually Bash, but if your
        machine is set up differently you can run it by opening a
        terminal and typing <code>bash</code>.  There is no need to
        install anything.
      </p>
    </div>
  </div>
</div> {% comment %} End of 'shell' section. {% endcomment %}


{% comment %} {% endcomment %}
<div id="scw">
  <h3>Supercomputing Wales</h3>
  
  In this workshop we will use the Supercomputing Wales facilities to
  learn to use High-Performance Computing. For this, you will need an
  account on the Supercomputing Wales facilities.
  
  <ol>
    <li>Visit <a href="https://my.supercomputing.wales/">My
    Supercomputing Wales</a></li>
	<li>Sign in with your Swansea University email and password</li>
	<li>Fill in the form requesting a Supercomputing Wales
    account. Your aaccount request will be processed by an
    administrator.</li>
	<li>Once you receive an email indicating that your account has been
    created, then revisit <a
    href="https://my.supercomputing.wales/">My Supercomputing
    Wales</a>, and log in again if necessary.</li>
	<li>Click the "Reset SCW Password" button, and enter a password
    that you will use to access the Supercomputing Wales
    hardware. (This does not have to be the same as your Swansea
    University password.) Click Submit.</li>
	<li>Under "Join a project", enter {{page.scw_project}} as the
    project code for this training session, and click "Join".</li>
  </ol>
</div> {% comment %} End of 'Supercomputing Wales' section. {% endcomment %}

{% if page.carpentry == "sa2c" %}
{% comment %} {% endcomment %}
<div id="filezilla">
  <h3>FileZilla</h3>

  We will use FileZilla to transfer files to and from the Supercomputing Wales facilities.

  <div class="row">
    <div class="col-md-4">
      <h4 id="filezilla-windows">Windows</h4>
      <ol>
        <li>Open <a href="https://filezilla-project.org/download.php?platform=win64">https://filezilla-project.org/download.php?platform=win64</a> with your web browser.</li>
	<li>Download and run the installer. You only need FileZilla, not FileZilla Pro.</li>
	<li>Follow the on-screen instructions. Note that while the installer may try to convince you to install additional software, you do not need to agree to this; if you do not agree to the additional license agreement, FileZilla will still install.</li>
      </ol>
    </div>
    <div class="col-md-4">
      <h4 id="filezilla-mac">macOS</h4>
      <ol>
        <li>Open <a href="https://filezilla-project.org/download.php?platform=osx">https://filezilla-project.org/download.php?platform=osx</a> with your web browser.</li>
	<li>Download and open the Client bundle. You only need FileZilla, not FileZilla Pro.</li>
	<li>Copy the FileZilla app to your Applications folder.</li>
      </ol>
    </div>
    <div class="col-md-4">
      <h4 id="filezilla-linux">Linux</h4>
      <ol>
        <li>Search for and install FileZilla in your distribution's package manager.</li>
      </ol>
    </div>
  </div>
</div>
{% comment %} End of 'FileZilla' section {% endcomment %}
{% endif %}

{% comment %}
<div id="vm">
  <h3>Virtual Machine</h3>

  <p>
    Some instructors prefer to have learners use a virtual machine (VM)
    rather than install software on their own computers.  If your
    instructors have chosen to do this, please:
  </p>
  <ol>
    <li>
      Install <a href="https://www.virtualbox.org/">VirtualBox</a>.
    </li>
    <li>
      Download our <a href="{{site.swc_vm}}">VM image</a>.
      <strong>Warning:</strong> this file is 1.7 GByte, so please
      download it <em>before</em> coming to your workshop.
    </li>
    <li>
      Load the VM into VirtualBox by selecting "Import Appliance" and
      loading the <code>.ova</code> file.
    </li>
  </ol>
</div>
{% endcomment %}



<h3 id="videoconferencing">Install the videoconferencing client</h3>

{% comment %}
Replace the paragraph below with the relevant installation instructions
if you do not use Zoom
{% endcomment %}
<p>
  If you haven't used Zoom before, go to the
  <a href="https://zoom.us/download">official website</a>
  to download and install the Zoom client for your computer.
</p>


<h4>Set up your workspace</h4>

<p>
  Like other Carpentries workshops,
  you will be learning by "coding along" with the Instructors.
  To do this, you will need to have both the window for the tool
  you will be learning about (a terminal, RStudio, your web browser, etc..)
  and the window for the Zoom video conference client open.
  In order to see both at once,
  we recommend using one of the following set up options:
  <ul>
    <li><strong>Two monitors:</strong> If you have two monitors,
      plan to have your terminal up on one monitor and
      the video conferencing software on the other.</li>
    <li><strong>Two devices:</strong> If you don't have two monitors,
      do you have another device (tablet, smartphone) with a medium to large
      sized screen? If so, try using the smaller device as your video
      conference connection and your larger device (laptop or desktop)
      to follow along with the tool you will be learning about.</li>
    <li><strong>Divide your screen:</strong> If you only have one device
      and one screen, practice having two windows
      (the video conference program and one of the tools you will be using
      at the workshop) open together.
      How can you best fit both on your screen?
      Will it work better for you to toggle between them
      using a keyboard shortcut?
      Try it out in advance to decide what will work best for you.</li>
  </ul>
  This <a href="https://carpentries.org/blog/2020/06/online-workshop-logistics-and_screen-layouts/" target="_blank">blog post</a> includes detailed information on how to set up your screen to follow along during the workshop.
</p>
