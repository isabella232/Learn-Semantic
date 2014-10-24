  ---
layout      : 'default'
css         : 'guide'

title       : 'Expert Guide'
description : 'Using Semantic UI in a production environment'
type        : 'Getting Started'
---
<%- @partial('header') %>

<div class="main container">

  <h2 class='ui header'>
    Getting Semantic UI
  </h2>

  <p>For links to download Semantic UI, check our our <a href="/guide/download.html">download page</a>.</p>

  <h2 class='ui header'>
    Setting Up
  </h2>

  <h3 class="ui header">Dependencies</h3>
  <p>Theming Semantic requires using build tools. After getting Semantic, you will need to install <a href="http://nodejs.org/download/" target="_blank">nodejs</a> and <a href="https://github.com/gulpjs/gulp/" target="_blank">gulp</a> to run the build process.</p>

  <p>Once you're up and running. Navigate to the semantic directory and install the npm dependencies</p>
  <div class="bash code">
    # install dependencies
    npm install
    # start install script
    gulp
  </div>

  <h3 class="ui header">Installing Semantic</h3>

  <img class="ui image" src="https://camo.githubusercontent.com/b9662e806f832c1ed8cb4c4d0e259fbcae20c222/68747470733a2f2f646c2e64726f70626f7875736572636f6e74656e742e636f6d2f752f323635373030372f696e7374616c6c2e676966">


  <p>The first time you run gulp you will be greeted with an interactive installer</p>
  <div class="bash code">
    # install
    gulp
  </div>

  <p>The installer will let you select which components to include, and specify paths for your project.<p>

  <table class="ui definition table">
    <thead>
      <th></th>
      <th>Installation Type</th>
    </thead>
    <tbody>
    <tr>
      <td>Automatic</td>
      <td>Installation will use the default paths, outputing css files to <code>dist/</code> and packaging all components together</td>
    </tr>
    <tr>
      <td>Express</td>
      <td>Will let you move your site folder and your dist folder and select from a list of components to include in your concatenated release.</td>
    </tr>
    <tr>
      <td>Custom</td>
      <td>Will prompt you for all available options</td>
    </tr>
    </tbody>
  </table>

  <p>The install process will create two files: <code>semantic.json</code> stores paths for your build  and sits on the top-level of your project, <code>theme.config</code> is a <b>LESS</b> file that exists in <b>src/</b> and allows you to centrally set the themes for each UI component.</p>

  <p>The installer will also create a special <b>site</b> folder, which contains your site-specific themes. The default location for this is <code>src/site</code>. For more information on using site themes, see the theming guide below.</p>

  <p>If you prefer these files and folders can be moved manually instead of using the installer.</p>
  <div class="bash code">
    mv semantic.json.example semantic.json
    mv src/theme.config.example src/theme.config
    mv src/_site src/site
    vi semantic.json
  </div>

  <div class="ui info message">For a full list of settings for <b>semantic.json</b>, check the <a href="https://github.com/Semantic-Org/Semantic-UI/blob/1.0/tasks/defaults.js">defaults values</a> which it inherits from.</div>

  <h2 class="ui header">Using Semantic</h2>

  <h3 class="ui header">Gulp commands</h3>
  <p>After setting up your project you have access to several commands for building your css and javascript.</p>

  <div class="bash code">
    gulp # runs default task (watch)
    gulp watch # watches files for changes
    gulp build # builds all files from source
    gulp install # re-runs install
  </div>

  <p>Keep in mind semantic will automatically adjust urls in css and add vendor-prefixes as part of the build process. This means <b>definitions and theme files do not need vendor prefixes</b>.</p>

  <div class="ui info message">
    <h4 class="ui header">Advanced Usage</h4>
    <p>In addition to the paths set in <code>semantic.json</code>, you can serve files to a second location, for example, a docs instance by using a separate config file <code>tasks/admin/docs.json</code>. Using a copy of the SUI documentation may work well internally for creating a style guide to hack on the theme designs for your project.</p>
    <div class="bash code">
      gulp serve-docs
      gulp build-docs
    </div>
  </div>

  <h2 class="ui header">Theming Semantic</h2>
  <p>
    Semantic uses an inheritance system similar to <a href="https://www.sublimetext.com/docs/2/settings.html" target="_blank">Sublime Text</a> designed to facilitate an ecosystem of theming
  </p>

  <div class="ui three fluid steps">
    <div class="step">
      <i class="lock icon"></i>
      <div class="content">
        <div class="title">Semantic</div>
        <div class="description">Library Defaults</div>
      </div>
    </div>
    <div class="step">
      <i class="download icon"></i>
      <div class="content">
        <div class="title">Theme</div>
        <div class="description">Downloadable Packages</div>
      </div>
    </div>
    <div class="step">
      <i class="user icon"></i>
      <div class="content">
        <div class="title">Site</div>
        <div class="description">User's Overrides</div>
      </div>
    </div>
  </div>

  <p>Semantic definitions are written using <b>LESS</b>.</p>
  <p>Don't use <code>LESS</code> in your dev environment? Don't worry, the only CSS preprocessor features used in Semantic under the hood are <b>css variables</b>, functions to modify colors, and <b>@import</b> to implement  inheritance.</p>

  <h2 class="ui header">Extending Semantic</h2>

  <p>Writing definitions while designing new interface elements is similar to <a href="http://en.wikipedia.org/wiki/Test-driven_development">test driven development</a> when writing code. Definitions are a rubric for all possible ways an element can appear visually.</p>

  <p>Creating UI definitions lets you create components that are <b>self documenting</b> so that other team-members working on your project can develop with them immediately without examining the codebases</p>


</div>