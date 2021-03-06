See a minimal working example at http://stanford.edu/~bwaldon/cgi-bin/afs_exp/index.html

# How it works

A PHP script (`collectdata.php`) collects a participant's data and saves their results as a .txt file on your web server. Participants are also provided a participation code which is identical to the name of their results file (this code is also written to `participant_codes.txt`). To claim compensation, participants enter their participation code on, e.g., MTurk or Prolific Academic. 

# Instructions

## Step 1: find an appropriate (i.e. PHP-enabled) web hosting service.

One option for Stanford affiliates is the Andrew File System (AFS). See here about how to request AFS services at Stanford: https://uit.stanford.edu/service/afs 

Should you choose to use AFS, you'll also need to enable the Stanford Common Gateway Interface (CGI) service. More on enabling CGI here: https://uit.stanford.edu/service/cgi

## Step 2: Design your experiment offline. 

Hint: a nice feature about the 245B experiment templates is that you can preview the data that would be saved if your experiment were live. By default, your script won't do this - after a particpant completes the study, they're redirected to `collectdata.php` (note that PHP won't work on a local machine - you'll probably just see raw code in your browser). If you want to preview your results and not redirect to the PHP script, open up `_shared/js/mmturkey.js` and change line 116...

`if (false) {`

to: 

`if (true) {`

Make sure to change this back to `if (false) {` before going on to step 3. 

## Step 3: Put your experiment online 

Upload your experiment folder to the appropriate place provided by your web hosting service. For Stanford AFS users, this is the `cgi-bin` directory (PHP won't work elsewhere on AFS). 

## Step 4: Link your experiment URL from MTurk, Prolific, etc.

Last I checked, MTurk has an 'external survey' template with a place for workers to enter a participation code. 
