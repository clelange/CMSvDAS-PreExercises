---
title: "First set"
teaching: 0
exercises: 0
questions:
- "Key question (FIXME)"
objectives:
- "First learning objective. (FIXME)"
keypoints:
- "First key point. Brief Answer to questions. (FIXME)"
---

\<style type=\"text/css\" media=\"all\"\> pre { text-align: left;
padding: 10px;margin-left: 20px; color: black; } pre.command
{background-color: lightgrey;} pre.cfg {background-color: lightblue;}
pre.code {background-color: lightpink;} pre.output {background-color:
lightgreen;}

\</style\>

CMS Data Analysis School Pre-Exercises - First Set {#cms-data-analysis-school-pre-exercises---first-set .unnumbered}
==================================================

[]{.twiki-macro .TOC title="Contents:"}

Introduction
------------

Welcome to the first set of CMS Data Analysis School (CMSDAS)
pre-exercises. The purpose of these exercises is to become familiar with
the basic software tools required to perform physics analysis at the
school. Please run and complete these exercises. Questions for each
exercise are in []{.twiki-macro .RED} red []{.twiki-macro .ENDCOLOR}
font. Submit your answers in the online response form available from
**the course web area** - For CMSDAS\@CERN 2020, **virtual**, the
complete set of links can be found at the [CMSDAS pre-exercises indico
page](https://indico.cern.ch/event/886923/). A large amount of
additional information about these exercises is available in the twikis
that we reference. Please remember that twikis evolve but aim to provide
the best information at any time.

%RED%The CMSDAS exercises (pre-exercises as well as exercises during the
school) are intended to be as generic as possible. However, CMSDAS is
held at different CMS collaborating institutes - e.g. CERN, the LPC at
Fermilab, DESY, etc.) Participants are expected to **request and obtain
local (at the intended school location) computer accounts** well in
advance of the school start date, to ensure they will be able to work
right away. It is very important for participants to use the
pre-exercises as a setup tool, so we recommend for everyone to **use the
laptop they intend to bring with them at the school** (NO
computer/laptop will be provided at the school), and to **connect to the
local computing resources that will be used for the school**. In most
cases laptops will need to be registered to be used in the local school
network, so please make sure you take care of this aspect too.

There are several sets of pre-exercises. As outlined above, if you are
going through the pre-exercises in preparation to attending a CMSDAS, we
strongly recommend using the laptop you intend to bring to the school
and logging into the cluster local to the school.

For the exercises that will be done during the school, instructions on
those exercises will be found on twikis similarly to the pre-exercises.

### Support

If you have not used the Linux command line before, you may learn more
at [WorkBookBasicLinux](CMSPublic.WorkBookBasicLinux)

#### Discord (chat)

There is a dedicated Discord server, called CMSDAS, setup to facilitate
communication and discussions via live chat (which is also archived).
The channel is hosted by the Discord app (<https://discord.com>).

The pre-exercises channel is available once you join or switch to the
CMSDAS server: <https://discord.gg/TcecvUF>

Note that you can access Discord via browser or you can download the
corresponding application running standalone on your laptop or
smartphone.

Obtain a computer account
-------------------------

To get a CERN account, please have a look at [Get Account at
CERN](CMSPublic.WorkBookGetAccount). Obtaining a CERN account can be
time-consuming and requires response from people at CERN during CERN
business hours. CERN is closed Dec. 21, 2019 - Jan. 5, 2020. CERN
account application starts with the institutional team leader filling
out a pre-registration form, so your institutional team leader also
needs to be available for this task.

**NOTE**: If you need an account elsewhere, you need to contact your
local cluster admins and follow their instructions.

### Obtain a Grid Certificate and CMS VO registration

-   A Grid Certificate and CMS VO registration will be needed for the
    next set of exercises. The registration process can be
    time-consuming (actions by several people are required), so it is
    important to start it as soon as possible. There are two main
    requirements which can be simply summarized: A certificate ensures
    that you are who you claim to be. A registration in the VO
    recognizes your (identified by your certificate) as a member of CMS.
    Both are needed to submit jobs on the Grid and access files remotely
    using xrootd.

Use the following link for this: [Get Your Grid Certificate and
CMSVO](https://twiki.cern.ch/twiki/bin/view/CMSPublic/SWGuideLcgAccess#Getting_a_personal_certificate).

### Obtain a github account

Since Summer 2013, most of the CMS software are hosted on
[Github](https://github.com). Github is a Git repository web-based
hosting service, while Git is a distributed revision control system. In
your future analysis work, version control of your analysis code will
become a very important task and git will be very useful. A small git
tutorial will wait for you in the fifth exercise set.

In order to checkout and develop CMS software, you will need a github
account, which is free.

-   In case you don't have one already, simply go to:
    <https://github.com/join> and follow the instructions to create a
    new account. Make sure you use a username people can recognize you
    easily or to specify your real name.
-   In case you already have an account you can simply use "the Sign in"
    dialog and put your username and password.
    <https://github.com/login>
-   %RED%Make sure you []{.twiki-macro .ENDCOLOR} [register your ssh key
    in
    Github](https://help.github.com/articles/adding-a-new-ssh-key-to-your-github-account/).
    (You don\'t need to use an ssh-agent, but you can try if you want
    to. For more about ssh-agents, see:
    [CMSGitTutorial\#SSH\_agent\_in\_logon\_file](CMSGitTutorial#SSH_agent_in_logon_file))
-   You will learn more about Github in the
    [SWGuideCMSDataAnalysisSchoolPreExerciseFifthSet](SWGuideCMSDataAnalysisSchoolPreExerciseFifthSet)

**NOTE:** Legend of colors for this tutorial:

``` {.command style="font-size: 13px"}
GRAY background for the commands to execute  (cut&paste)
```

``` {.output style="font-size: 13px"}
GREEN background for the output sample of the executed commands
```

``` {.cfg style="font-size: 13px"}
BLUE background for the configuration files  (cut&paste)
```

``` {.code style="font-size: 13px"}
PINK background for the code (EDAnalyzer etc.)  (cut&paste)
```

Exercise 1 - Cut and Paste
--------------------------

**Note**: This exercise is designed to run only on **lxplus** and
**cmslpc** as copies of the scripts are present there. Elsewhere, one
can certainly copy the script and try.

As the exercises often require copying and pasting from instruction, we
will make sure that you will have no problems. To verify if cut and
paste to/from a terminal window works, first copy the script
`runThisCommand.py` as follows.

For `lxplus` you could try the following commands: []{.twiki-macro
.TWISTY mode="div" showlink="Show " hidelink="Hide " firststart="hide"
showimgright="%ICONURLPATH{toggleopen-small}%"
hideimgright="%ICONURLPATH{toggleclose-small}%"}

``` {.command}
ssh -Y USERNAME@lxplus.cern.ch
USERNAME@lxplus.cern.ch's password:
```

Enter the password and then do:

``` {.command}
cp /afs/cern.ch/cms/Tutorials/TWIKI_DATA/runThisCommand.py .
```

[]{.twiki-macro .ENDTWISTY}

and then cut and paste the following and then hit return

``` {.command}
./runThisCommand.py "asdf;klasdjf;kakjsdf;akjf;aksdljf;a" "sldjfqewradsfafaw4efaefawefzdxffasdfw4ffawefawe4fawasdffadsfef"
```

The response should be your username followed by alphanumeric string of
characters unique to your username, for example for a user named
gbenelli:

``` {.output}
success: gbenelli toraryyv
```

[]{.twiki-macro .RED} QUESTION 1 - Post the alphanumeric string of
characters unique to your username.[]{.twiki-macro .ENDCOLOR}

If you executed the command without copy-pasting:

``` {.command}
./runThisCommand.py
```

the command will return:

``` {.output}
Error: You must provide the secret key
```

Alternately, copying incorrectly will return

``` {.output}
Error: You didn't paste the correct input string
```

Exercise 2 - Simple Edit Exercise
---------------------------------

[]{.twiki-macro .RED} **Note**: This exercise is designed to run only on
**lxplus**, **cmslpc**, **Pisa**, and **Taipei** as the scripts are
present there. Elsewhere, one can certainly copy the script and try.
[]{.twiki-macro .ENDCOLOR}

The purpose of this exercise is to ensure that the user can edit files.
%RED%This means that you need to be able to use one of the standard text
editors (emacs, pico, nano, vi, vim, etc.) available on the cluster you
are running (**lxplus**, **cmslpc-sl7**, \...), open a file, edit it and
save it%ENDCOLOR%

On lxplus:

``` {.command}
cp /afs/cern.ch/cms/Tutorials/TWIKI_DATA/editThisCommand.py .
```

Then open `editThisCommand.py` with your favorite editor (e.g.
`emacs -nw editThisCommand.py`) and make sure that the 11th line has
\<tt\> \# \</tt\>(hash character) as the first character of the line. If
not, explicitly change the following three lines:

``` {.cfg}
# Please comment the line below out by adding a '#' to the front of
# the line.
raise RuntimeError, "You need to comment out this line with a #"
```

to:

``` {.cfg}
# Please comment the line below out by adding a '#' to the front of
# the line.
#raise RuntimeError, "You need to comment out this line with a #"
```

Save the file (e.g. in emacs `CTRL+x CTRL+s` to save, `CTRL+x CTRL+c` to
quit the editor) and execute the command:

``` {.command}
./editThisCommand.py
```

If this is successful, the result will be:

``` {.output}
success:  gbenelli 0x6D0DB4E0
```

[]{.twiki-macro .RED} QUESTION 2 - Paste the line beginning with
\"success\" into the form provided. []{.twiki-macro .ENDCOLOR}

If the file has not been successfully edited, an error message will
result such as:

``` {.output}
Traceback (most recent call last):
  File "./editThisCommand.py", line 11, in ?
    raise RuntimeError, "You need to comment out this line with a #"
RuntimeError: You need to comment out this line with a #
```

You will first want to set up the proper environment by entering the
following commands, depending on what shell you use:

for bash shell:

``` {.command}
source /cvmfs/cms.cern.ch/cmsset_default.sh
export CMSSW_GIT_REFERENCE=/cvmfs/cms.cern.ch/cmssw.git.daily
```

OR for tcsh shell:

``` {.command}
source /cvmfs/cms.cern.ch/cmsset_default.csh
setenv CMSSW_GIT_REFERENCE /cvmfs/cms.cern.ch/cmssw.git.daily
```

Actually you should edit your \~/.tcshrc file (or \~/.bash\_profile if
bash is your default shell), create it if you do not have one, to
include the above commands so that you do not have to execute each time
you log into the cluster. %RED%\*Note\*[]{.twiki-macro .ENDCOLOR} If you
wish to change your default shell, use the method [Documented here in
the setup software
instructions](https://uscms.org/uscms_at_work/physics/computing/setup/setup_software.shtml#shell).
A shell change will take up to 1 business day to complete.

Then proceed with the creation of a working area (called YOURWORKINGAREA
in the following):

``` {.command}
<!-- L. Cristella for CERN 2020
cd ~/nobackup
-->
mkdir YOURWORKINGAREA
cd YOURWORKINGAREA
### If you are using the default tcsh shell (or csh shell)
setenv SCRAM_ARCH slc7_amd64_gcc700
### Alternatively, If you are using Bash shell
export SCRAM_ARCH=slc7_amd64_gcc700
cmsrel CMSSW_10_6_4
cd CMSSW_10_6_4/src
cmsenv
```

To be able to check out specific CMSSW packages from Github, you will
need to configure your local account following the [FifthSet PreExecises
Git
configuration](https://twiki.cern.ch/twiki/bin/view/CMS/SWGuideCMSDataAnalysisSchoolPreExerciseFifthSet#Git%20configuration).
You only have to do this command once for a cluster you are working on:

``` {.command}
git config --global user.name [Name]
git config --global user.email [Email]
git config --global user.github [Account]
```

Now you can initialize the CMSSW area as a local git repository.

``` {.command}
git cms-init
```

This last command will take some time to execute and will produce some
long output, be patient.

Every time you log out or exit a session you will need to setup your
environment in your working directory again. To do so, once you have
executed once the steps above (assuming you have added the
`source /cvmfs/cms.cern.ch/cmsset_default.csh #or .sh for bash` in your
\~/.tcshrc or \~/.bash\_profile file), you simply:

``` {.command}
<!-- L. Cristella for CERN 2020
cd ~/nobackup/YOURWORKINGAREA/CMSSW_10_6_4/src
-->
cd ~/YOURWORKINGAREA/CMSSW_10_6_4/src
cmsenv
```

And you are ready to go!

Exercise 4 - Find data in the DAS ( Data Aggregation Service)
-------------------------------------------------------------

In this exercise we will locate the MC dataset **RelValZMM** and the
collision dataset **/DoubleMuon/Run2018A-PromptReco-v1/MINIAOD** using
the **Data Aggregation Service** (not to be confused with the **Data
Analysis School** in which you are partaking). Also be aware that DAS is
an improved database access service known many years ago as DBS (Dataset
Bookkeeping System).

Go to the url [DAS](https://cmsweb.cern.ch/das/), **NOTE** that you will
be asked for your Grid certificate which you should have loaded into
your browser by now, (also note that there may be a security warning
message, which you will need to ignore and still load the page) and type
in the space provided:

`dataset release=CMSSW_10_6_4 dataset=/RelValZMM*/*CMSSW_10_6_4*/MINIAOD*`

This will search for datasets, processed with release `CMSSW_10_6_4`,
which is named like `/RelValZMM*/*CMSSW_10_6_4*/MINIAOD*`. The syntax
for searches is found [here](https://cmsweb.cern.ch/das/faq), with many
useful common search patterns under \"CMS Queries\".

For this query, several results should be displayed (you may be queried
for security exceptions in the process). Select (click) on the dataset
name
**/RelValZMM\_13/CMSSW\_10\_6\_4-PUpmx25ns\_106X\_upgrade2018\_realistic\_v9-v1/MINIAODSIM**
and after a few seconds another page will appear.

[]{.twiki-macro .RED} QUESTION 4.1a - What is the size of this dataset?
[]{.twiki-macro .ENDCOLOR}

[]{.twiki-macro .RED} QUESTION 4.1b Click on \"Sites\" to get a list of
sites hosting this data. Is this data at FNAL? Is this data at DESY?
[]{.twiki-macro .ENDCOLOR}

Back in the main dataset page, click on the link \"Files\" to get a list
of the root files in our selected dataset. One of the files it contains
should look like this:

    /store/relval/CMSSW_10_6_4/RelValZMM_13/MINIAODSIM/PUpmx25ns_106X_upgrade2018_realistic_v9-v1/10000/DBE18AD9-E36D-B449-B659-A71362DAC57A.root

If you want to know the name of the dataset from the name of a file, one
can go to [DAS](https://cmsweb.cern.ch/das/) and type

`dataset file=/store/relval/CMSSW_10_6_4/RelValZMM_13/MINIAODSIM/PUpmx25ns_106X_upgrade2018_realistic_v9-v1/10000/DBE18AD9-E36D-B449-B659-A71362DAC57A.root`

in the command line and hit \"Enter\".

Now we will locate a collisions dataset skim using the keyword search
which is sometimes more convenient if you know the dataset you are
looking for.

In [DAS](https://cmsweb.cern.ch/das/), type

`dataset=/DoubleMu*/*Run2018A*/MINIAOD*`

and hit Enter. Answer the following question:

[]{.twiki-macro .RED} QUESTION 4.2 - What release was the dataset
containing PromptReco -v1 collected in? []{.twiki-macro .ENDCOLOR} (If
you see more than one release, just answer one)

Having set your CMSSW environment one can also search for the dataset
**/DoubleMuon/Run2018A-PromptReco-v1/MINIAOD** by invoking the DAS
command in your `WORKING DIRECTORY`. The DAS command `dasgoclient` is in
the path for CMSSW\_9\_X\_Y versions and above, so you do not need to
download anything additional. More about `dasgoclient` can be found
[here](https://cmsweb.cern.ch/das/faq).

The query we\'re interested in is:
**/DoubleMuon/Run2018A-PromptReco-v1/MINIAOD**, see the commands below
on how to execute it command-line. This assumes that you have installed
your CERN grid certificate .

``` {.command}
voms-proxy-init --voms cms
```

(You will be asked for your grid certificate passphrase). Then you can
execute the query with:

``` {.command}
dasgoclient --query="dataset=/DoubleMuon*/Run2018A-PromptReco-v1/MINIAOD" --format=plain
```

You will see something like []{.twiki-macro .TWISTY mode="div"
showlink="Show result..." hidelink="Hide result..." remember="on"
showimgleft="%ICONURLPATH{toggleopen-small}%"
hideimgleft="%ICONURLPATH{toggleclose-small}%"}

``` {.output}
/DoubleMuon/Run2018A-PromptReco-v1/MINIAOD
/DoubleMuonLowMass/Run2018A-PromptReco-v1/MINIAOD
```

[]{.twiki-macro .ENDTWISTY}

More information about accessing data in the [Data Aggregation
Service](https://cmsweb.cern.ch/das/faq) can be found in
[WorkBookDataSamples](CMSPublic.WorkBookDataSamples)

Exercise 5 - EDM ( Event Data Model framework) standalone utilities -
---------------------------------------------------------------------

`edmFileUtil`, `edmDumpEventContent`, `edmProvDump`, `edmEventSize`

The overall collection of CMS software, referred to as
[CMSSW](CMSPublic.WorkBookCMSSWFramework), is built around a Framework,
an Event Data Model ( [EDM](CMSPublic./WorkBookCMSSWFramework#EdM)), and
Services needed by the simulation, calibration and alignment, and
reconstruction modules that process event data so that physicists can
perform analysis. The primary goal of the Framework and EDM is to
facilitate the development and deployment of reconstruction and analysis
software. The CMS Event Data Model (EDM) is centered around the concept
of an Event. An Event is a C++ object container for all RAW and
reconstructed data related to a particular collision.To understand what
is in a data file and more, several EDM utilities are available. In this
exercise, one will use three of these EDM utilities. They will be very
useful at CMSDAS and after. More about these EDM utilities can be found
at [WorkBookEdmUtilities](CMSPublic.WorkBookEdmUtilities). These
together with the [Github web interface for
CMSSW](https://github.com/cms-sw/cmssw) and the [CMS LXR Cross
Referencer](https://cmssdt.cern.ch/lxr/) are very useful to understand
and write CMS code.

### edmFileUtil

First we will use the `edmFileUtil` to find the **physical file name**
(PFN) where the file is actually stored at your site, given the
**logical file name** (LFN) which is an alias that can be used in CMSSW
at any site.

-   Use `edmFileUtil` to find the **physical file name** (PFN)
    corresponding to the **logical file name** (LFN) from a MiniAOD
    file.
    -   To do this execute \<verbatim class=\"command\"\>edmFileUtil -d
        /store/relval/CMSSW\_10\_6\_4/RelValZMM\_13/MINIAODSIM/PUpmx25ns\_106X\_upgrade2018\_realistic\_v9-v1/10000/DBE18AD9-E36D-B449-B659-A71362DAC57A.root\</verbatim\>

```{=html}
<!-- -->
```
-   If you are working on lxplus this will return: \<pre
    class=\"output\"\>\<verbatim\>
    root://eoscms.cern.ch//eos/cms/store/relval/CMSSW\_8\_1\_0\_pre6/RelValZMM\_13/MINIAODSIM

/80X\_mcRun2\_asymptotic\_v14-v1/00000/1C304FCA-FC2D-E611-8856-0025905B856C.root\</verbatim\>\</pre\>
\</verbatim\> \</pre\>

### edmDumpEventContent

Next we will use `edmDumpEventContent` to dump a summary of the products
that are contained within the file we\'re interested in, on **lxplus**
or **cmslpc-sl7**:

-   Use `edmDumpEventContent` to see what class names etc. to use in
    order to access the objects in the MiniAOD file. If you want to look
    at a specific object (say, `slimmedMuons`) then execute \<pre
    class=\"command\"\> edmDumpEventContent \--all \--regex slimmedMuons
    root://cmsxrootd.fnal.gov//store/user/cmsdas/2019/pre\_exercises/0EE14BA8-41BB-E611-AD2F-0CC47A4D760A.root
    \</pre\>

This will return:

    Type                   Module           Label     Process        Full Name
    --------------------------------------------------------------------------
    vector<pat::Muon>      "slimmedMuons"   ""        "RECO"         patMuons_slimmedMuons__RECO

-   The output of `edmDumpEventContent` has information divided into
    four variable width columns. The first column is the C++ class
    `type of the data`, the second is `module label`, the third is
    `product instance label` and the fourth is `process name`. More
    information is available at [Identifying Data in the
    Event](CMSPublic.WorkBookCMSSWFramework#ModularEvtContent).
    -   []{.twiki-macro .RED} QUESTION 5.1a - How many modules produce
        products of type `vector` ? []{.twiki-macro .ENDCOLOR}
    -   []{.twiki-macro .RED} QUESTION 5.1b - What are the names of
        three of the modules that produce products of type `vector`?
        []{.twiki-macro .ENDCOLOR}
    -   NOTE: Instead of the above, try without the option
        `--regex slimmedMuons` . This will dump the entire event
        content - a file with many lines. For this reason we\'ll send
        the output to a file called `EdmDumpEventContent.txt` with a
        UNIX pipe command.

```{=html}
<!-- -->
```
-   To do this on lxplus execute \<verbatim class=\"command\"\>
    edmDumpEventContent
    /store/relval/CMSSW\_8\_1\_0\_pre6/RelValZMM\_13/MINIAODSIM/80X\_mcRun2\_asymptotic\_v14-v1/00000/1C304FCA-FC2D-E611-8856-0025905B856C.root \>
    EdmDumpEventContent.txt \</verbatim\>

### edmProvDump

To aid in understanding the full history of an analysis, the framework
accumulates provenance for all data stored in the standard ROOT output
files. Using the command `edmProvDump` one can print out all the tracked
parameters used to create the data file. For example, one can see which
modules were run and the CMSSW version used to make the MiniAOD file. In
executing the command below it is important to follow the instructions
carefully, otherwise a large number of warning messages may appear. The
`ROOT` warning messages can be ignored.

-   To do this execute on lxplus: \<verbatim class=\"command\"\>
    edmProvDump
    /store/relval/CMSSW\_8\_1\_0\_pre6/RelValZMM\_13/MINIAODSIM/80X\_mcRun2\_asymptotic\_v14-v1/00000/1C304FCA-FC2D-E611-8856-0025905B856C.root \>
    EdmProvDump.txt \</verbatim\>

```{=html}
<!-- -->
```
-   NOTE: `EdmProvDump.txt` is a very large file of the order of
    40000-60000 lines. Open and look at this file and locate
    `Processing History` ( about 20-40 lines from the top).
-   []{.twiki-macro .RED} QUESTION 5.2 - Which version of CMSSW*?*?\_?
    was used to produce the MiniAOD file? []{.twiki-macro .ENDCOLOR}

### edmEventSize

Finally we will execute `edmEventSize` to determine the size of
different branches in the data file. Further details may be found here:
CMSPublic.SWGuideEdmEventSize. `edmEventSize` isn\'t actually a \'Core\'
helper function (anyone can slap \'edm\' on the front of a program in
CMSSW). You can use edmFileUtil to get a PFN from an LFN (as shown
above) so you could combine the call

-   Execute on lxplus: \<verbatim class=\"command\"\> edmEventSize -v
    \`edmFileUtil -d
    /store/relval/CMSSW\_7\_3\_0\_pre1/RelValZMM\_13/MINIAODSIM/PU50ns\_PRE\_LS172\_V16-v1/00000/5E363364-FD5E-E411-88D9-02163E0104D0.root\` \>
    EdmEventSize.txt \</verbatim\>

```{=html}
<!-- -->
```
-   []{.twiki-macro .RED} QUESTION 5.3 What is the number of events if
    you execute the command at **cmslpc-sl7**?[]{.twiki-macro .ENDCOLOR}
    \<\-- \* Execute on the KNU cluster \<verbatim class=\"command\"\>
    edmEventSize -v \`edmFileUtil -d
    /cmsdas/data/PreEX\_1/CMSDataAnaSch\_MiniAODZMM730pre1.root\` \>
    EdmEventSize.txt \</verbatim\>
-   Execute \<verbatim class=\"command\"\> edmEventSize -v \`edmFileUtil
    -d
    <file:/afs/cern.ch/cms/Tutorials/TWIKI_DATA/CMSDataAnaSch_Data_536.root>\` \>
    EdmEventSize.txt \</verbatim\> \--\>
-   Open and look at file `EdmEventSize.txt` and locate the line
    containing the text `patJets_slimmedJetsPuppi__RECO` . There are two
    numbers following this text that measure the plain and the
    compressed size of this branch.
-   []{.twiki-macro .RED} QUESTION 5.4 - What are these two numbers?
    []{.twiki-macro .ENDCOLOR}

Exercise 6 - Familiar with MiniAOD Format
-----------------------------------------

Analyzing physics data at CMS is a very complicated task involving
multiple steps, sharing of expertise, cross checks, and comparing
different analysis. To maximize physics productivity, CMS developed a
high-level data tier **MiniAOD** in Spring 2014 to serve the needs of
the mainstream physics analyses while keeping a small event size (30-50
kb/event), with easy access to the algorithms developed by Physics
Objects Groups (POGs) in the framework of the CMSSW offline software.
The production of MiniAODs will be done centrally for common samples.
Its goal is to centralize the production of PAT tuple which were used
among the Physics Analysis Groups (PAGs) in Run 1. (Information about
PAT can be found in CMSPublic.SWGuidePAT and in a [CMS conference
note](http://cdsweb.cern.ch/record/1196152).) MiniAOD samples will be
used in the Run 2 analysis. Hence it is important to know about this
tool. More information about MiniAOD can be found in
CMSPublic.WorkBookMiniAOD.

-   Note: A new data tier called **NanoAOD** has recently been
    developed. The goal of this tier is to centralize the ntuple
    production of \~50% of analyses and to keep the event size below
    2kb/event. However, this pre-exercise will not cover the use of
    NanoAOD. More information can be found at CMSPublic.WorkBookNanoAOD.

The main contents of the MiniAOD are:

-   High level physics objects (leptons, photons, jets,
    E\<sub\>T\</sub\>\<sup\>miss\</sup\>), with detailed information in
    order to allow e.g. retuning of identification criteria, saved using
    [PAT dataformats](WorkBookPATDataFormats).\
    Some preselection requirements are applied on the objects, and
    objects failing these requirements are either not stored or stored
    only with a more limited set of information.\
    Some high level corrections are applied: L1+L2+L3(+residual)
    corrections to jets, type1 corrections to
    E\<sub\>T\</sub\>\<sup\>miss\</sup\>.
-   The full list of particles reconstructed by the ParticleFlow, though
    only storing the most basic quantities for each object (4-vector,
    impact parameter, pdg id, some quality flags), and with reduced
    numerical precision; these are useful to recompute isolation, or to
    perform jet substructure studies.\
    For charged particles with p\<sub\>T\</sub\> \> 0.9 GeV, more
    information about the associated track is saved, including the
    covariance matrix, so that they can be used for b-tagging purposes.
-   MC Truth information: a subset of the
    [genParticles](CMSPublic.WorkBookGenParticleCandidate) enough to
    describe the hard scattering process, jet flavour information, and
    final state leptons and photons; GenJets with p\<sub\>T\</sub\> \> 8
    GeV are also stored, and so are the other mc summary information
    (e.g event weight, LHE header, PDF, PU information).\
    In addition, all the stable genParticles with mc status code 1 are
    also saved, to allow reclustering of GenJets with different
    algorithms and substructure studies.
-   Trigger information: MiniAOD contains the trigger bits associated to
    all paths, and all the trigger objects that have contributed to
    firing at least one filter within the trigger. In addition, we store
    all objects reconstructed at L1 and the L1 global trigger summary,
    and the prescale values of all the triggers.

Please note that the files used in the following are from older
releases, but they still illustrate the points they intended to. To
avoid the fact that RelVal files (produced to validate new release in
the rapid CMSSW development cycle) become unavailable on a short (month)
timescale, a small set of files have been copied to the LPC EOS storage.
They are available at
`root://cmseos.fnal.gov//store/user/cmsdas/2019/pre_exercises/`.

The Z to dimoun MC file
`root://cmseos.fnal.gov//store/user/cmsdas/2019/pre_exercises/CMSDataAnaSch_MiniAODZMM730pre1.root`
is made in `CMSSW_7_3_0_pre1` release and the datafile
`root://cmseos.fnal.gov//store/user/cmsdas/2019/pre_exercises/CMSDataAnaSch_Data_706_MiniAOD.root`
made from the collisions dataskim
**/DoubleMu/CMSSW\_7\_0\_6-GR\_70\_V2\_AN1\_RelVal\_zMu2011A-v1/MINIAOD**.

In your working directory, try to open the root file
`root://cmseos.fnal.gov//store/user/cmsdas/2019/pre_exercises/CMSDataAnaSch_MiniAODZMM730pre1.root`

``` {.command}
root -l
```

**NOTE**: remember to use the `-Y` option of the `ssh` command when
connecting to the cluster (Exercise 1), in order to access the graphical
browser requested in this exercise. **NOTE** if you already have a
custom `.rootrc` or `.rootlogon.C`, you can start root without them with
`root -l -n`

On the `ROOT` prompt type the following:

``` {.command}
gSystem-&gt;Load("libFWCoreFWLite.so");
FWLiteEnabler::enable();
gSystem-&gt;Load("libDataFormatsFWLite.so");
gROOT-&gt;SetStyle ("Plain");
gStyle-&gt;SetOptStat(111111);
<!--G.Benelli Dec 2016
%RED%If you are using lxplus or nafhh-cms:%ENDCOLOR%
TFile::Open("/afs/cern.ch/user/b/benwu/public/CMSDAS/CMSDataAnaSch_MiniAODZMM730pre1.root");
%RED%If you are at the LPC:%ENDCOLOR%
-->
TFile *theFile = TFile::Open("root://cmseos.fnal.gov//store/user/cmsdas/2019/pre_exercises/CMSDataAnaSch_MiniAODZMM730pre1.root");
<!--
%RED%If you are using KNUT2:%ENDCOLOR%
TFile::Open("/cmsdas/data/pre_exercises/Exe1/CMSDataAnaSch_MiniAODZMM730pre1.root");
-->
TBrowser b;
```

Note: TBrowser is a graphical browser. It runs on the computer, where
you started ROOT. Its graphical interface needs to be forwarded to your
computer. This can be very slow. You either need a lot of patience, a
good connection or you can try to run ROOT locally, copying the root
files that are to be inspected. Since everyone is running a different
operating system on their local computer, we do not support the setup of
ROOT on your local computer. However, instructions exist on the
[official ROOT website](https://root.cern.ch/downloading-root).

To be able to use the member functions of a CMSSW data class from within
ROOT, a \'dictionary\' for that class needs to be available to ROOT. To
obtain that dictionary, it is necessary to load the proper library into
ROOT. The first three lines of the code above do exactly that. More
information is at
[WorkBookFWLiteExamples](CMSPublic.WorkBookFWLiteExamples). Note that
`gROOT->SetStyle ("Plain");` sets a plain white background for all the
plots in ROOT.

NOTE: If the `rootlogon.C` is created in the home area, and the above
four lines of code are in that file, the dictionary will be obtained,
and all the plots will have a white background automatically upon
logging in to `ROOT`.

Now a `ROOT` browser window opens and looks like this (\"Root Files\"
may or may not be selected):

[]{.twiki-macro .TWISTY mode="div" showlink="Show result..."
hidelink="Hide result..." remember="on"
showimgleft="%ICONURLPATH{toggleopen-small}%"
hideimgleft="%ICONURLPATH{toggleclose-small}%"}

\<img alt=\"MiniAOD\_View1.png\"
src=\"%ATTACHURLPATH%/MiniAOD\_View1.png\" width=\"594\" /\>

[]{.twiki-macro .ENDTWISTY}

In this window click on `ROOT Files` on the left menu and now the window
looks like this: []{.twiki-macro .TWISTY mode="div"
showlink="Show result..." hidelink="Hide result..." remember="on"
showimgleft="%ICONURLPATH{toggleopen-small}%"
hideimgleft="%ICONURLPATH{toggleclose-small}%"}

\<img alt=\"MiniAOD\_View2.png\"
src=\"%ATTACHURLPATH%/MiniAOD\_View2.png\" width=\"594\" /\>
[]{.twiki-macro .ENDTWISTY}

Double-click on the root file you opened:
`root://cmseos.fnal.gov//store/user/cmsdas/2019/pre_exercises/CMSDataAnaSch_MiniAODZMM730pre1.root`,
then `Events`, then scroll down and click `patMuons_slimmedMuons__PAT`
(or the little + that appears next to it) and then
`patMuons_slimmedMuons__PAT.obj`. A window appears that looks like this:

[]{.twiki-macro .TWISTY mode="div" showlink="Show result..."
hidelink="Hide result..." remember="on"
showimgleft="%ICONURLPATH{toggleopen-small}%"
hideimgleft="%ICONURLPATH{toggleclose-small}%"}

\<img alt=\"MiniAOD\_View3.png\"
src=\"%ATTACHURLPATH%/MiniAOD\_View3.png\" width=\"594\" /\>
[]{.twiki-macro .ENDTWISTY}

Scroll a long way down the file (not too fast) and click on `pt()`. A
PAT Muon Pt distribution will appear. These muons have been produced in
the Z to mumu interactions as the name of the data sample implies.
[]{.twiki-macro .TWISTY mode="div" showlink="Show result..."
hidelink="Hide result..." remember="on"
showimgleft="%ICONURLPATH{toggleopen-small}%"
hideimgleft="%ICONURLPATH{toggleclose-small}%"}

\<img alt=\"MiniAOD\_View4.png\"
src=\"%ATTACHURLPATH%/MiniAOD\_View4.png\" width=\"594\" /\>
[]{.twiki-macro .ENDTWISTY}

\
[]{.twiki-macro .RED} QUESTION 6.1 - Which is the mean value of the muon
pt() for the MC data? []{.twiki-macro .ENDCOLOR}

\
[]{.twiki-macro .RED} Note: To exit ROOT simply type `.q` in the command
line.[]{.twiki-macro .ENDCOLOR}

Now open the data file
`root://cmseos.fnal.gov//store/user/cmsdas/2019/pre_exercises/CMSDataAnaSch_Data_706_MiniAOD.root`.
Similarly run the following command, and answer the following question:

``` {.command}
 root -l
```

On the `ROOT` prompt type the following:

``` {.command}
gSystem-&gt;Load("libFWCoreFWLite.so");
FWLiteEnabler::enable();
gSystem-&gt;Load("libDataFormatsFWLite.so");
gROOT-&gt;SetStyle ("Plain");
gStyle-&gt;SetOptStat(111111);
<!--G.Benelli Dec 2016
%RED%If you are using lxplus:%ENDCOLOR%
TFile::Open("/afs/cern.ch/user/b/benwu/public/CMSDAS/CMSDataAnaSch_Data_706_MiniAOD.root");

%RED%If you are at the LPC:%ENDCOLOR%
-->
TFile *theFile = TFile::Open("root://cmseos.fnal.gov//store/user/cmsdas/2019/pre_exercises/CMSDataAnaSch_Data_706_MiniAOD.root");

TBrowser b;
<!--
%RED%If you are using KNUT2:%ENDCOLOR%
TFile::Open("/cmsdas/data/pre_exercises/Exe1/CMSDataAnaSch_Data_706_MiniAOD.root");
-->
```

[]{.twiki-macro .RED} QUESTION 6.2 - What is the mean value of the muon
pt() for the collision data? []{.twiki-macro .ENDCOLOR}

Be sure to submit your answers to the [Google Form first
set](https://forms.gle/RBZ6faVi6xn7ZhHX7), then proceed to the second
set. Links to all exercises below:

Link to SWGuideCMSDASAtCERNPreExerciseSecondSet

Link to SWGuideCMSDASAtCERNPreExerciseThirdSet

Link to SWGuideCMSDASAtCERNPreExerciseFourthSet

Link to SWGuideCMSDASAtCERNPreExerciseFifthSet

Link to SWGuideCMSDASAtCERNPreExerciseSixthSet

-   [runThisCommand.py.txt](%ATTACHURL%/runThisCommand.py.txt): python
    scripts for questions 1 and 2\</verbatim\>

```{=html}
<!-- -->
```
-   [editThisCommand.py.txt](%ATTACHURL%/editThisCommand.py.txt): python
    scripts for questions 1 and 2\</verbatim\>

[]{.twiki-macro .TWISTY mode="div" showlink="Show " hidelink="Hide "
firststart="hide" showimgright="%ICONURLPATH{toggleopen-small}%"
hideimgright="%ICONURLPATH{toggleclose-small}%"}

  Reviewer/Editor and Date (copy from screen)   Comments
  --------------------------------------------- -------------------------------------------
  Main.AdrianPerieanu - 14 July 2016            Updated to CMSSW\_8\_0\_6 for <CMSDAS@HH>
  Main.MargueriteTonjes - 23 October 2017       Updates to 2017 data for <CMSDAS@LPC2018>
  Main.AlexxPerloff - 13 October 2018           Updates to twiki for <CMSDAS@LPC2019>
  Main.LeonardoCristella - 22 June 2020         Updates to twiki for <CMSDAS@CERN2020>

[]{.twiki-macro .REVIEW} Main.AlexxPerloff - 13 October 2018\
[]{.twiki-macro .ENDTWISTY}
