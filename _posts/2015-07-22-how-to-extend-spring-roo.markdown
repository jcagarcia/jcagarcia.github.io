---
layout:     post
title:      "How to increase Spring Roo power with advanced features"
subtitle:   "Introduction to Spring Roo Add-On Suites"
date:       2015-07-22 00:00:00
author:     "Juan Carlos García"
header-img: "img/green-bg.jpg"
---

<p>Since Spring Roo 2.0.0.M1 version, you are able to <b>increase the power</b> of your Spring Roo installation including advanced features.</p> 

<p>The way to do it is using new Spring Roo concept called "Spring Roo Add-On Suites". As you could read on <a href="http://docs.spring.io/spring-roo/docs/2.0.0.M1/reference/html/#roo-addon-suites">Spring Roo reference guide</a>:</p>

> A “Roo Addon Suite” is a great way to package and distribute a set of add-ons together, for example if you want to create advanced features that are not included in Spring Roo Shell by default.

<p>In this post I'm only going to show you how to include an external "Roo Add-On Suite" in your Spring Roo installation to extend Roo shell with advanced functionalities. In a future post, I will publish a tutorial about "How to create your own Roo Add-On Suite" and how to install it.</p>

<h3>Where can I found public Roo Add-On Suites?</h3>

<p>Since Spring Roo 2.0.0.M1 version, Spring Roo has its own <a href="http://projects.spring.io/spring-roo/marketplace/">Marketplace</a> where public Roo Add-On Suites will be published. Right now, only <a href="http://www.gvnix.org/en/index.html">gvNIX Roo Add-On Suite</a> is available to install it, but I hope that you could publish your own Roo Add-On Suite really soon ;)</p>

<img src="http://jcagarcia.github.io//img/gvnix-roo-addon-suite.png" />
<h3>Steps to include Roo Add-On Suite</h3>

<p>The process to include a "Roo Add-On Suite" on your Spring Roo distribution is really really easy. First of all, let's open Spring Roo 2.0.0.M1 shell:</p>

<img src="http://jcagarcia.github.io/img/spring-roo-2.0.0.M1-shell.png" />

<p>Now, you need to install the URL of the repository that contains the Roo Addon Suite, in this case gvNIX Roo Add-On Suite. To do that, you need to open <a href="http://projects.spring.io/spring-roo/marketplace/">Spring Roo Marketplace</a> and copy the "Repository Index URL" that you want to install:</p>

<img src="http://jcagarcia.github.io/img/repository-index-url.png" />

<p>When you have copied the repository index URL, you need to execute the following command on your Spring Roo Shell to install the repository:</p>

``roo> addon repository add --url http://repository.gvnix.org/index.xml``

<img src="http://jcagarcia.github.io/img/addon-repository-install.png" />

<p>To know how many Roo Addon Suites contains the repository, you need to run the command below:</p>

``roo> addon suite list --repository http://repository.gvnix.org/index.xml``

<img src="http://jcagarcia.github.io/img/addon-suite-list.png" />

<p>Let's install the gvNIX Roo Addon Suite that contains advanced features like jQuery, Bootstrap 3, Leaflet, DataTables, Dandelion DataTables, etc... To do that, execute the following command:</p>

``roo> addon suite install name --symbolicName org.gvnix.roo.addon.suite``

<img src="http://jcagarcia.github.io/img/addon-suite-install.png" />

<p>To validate that all the advanced features included on gvNIX Roo Add-On Suite were included on your Spring Roo installation, you could execute the following command:</p>

``roo> addon list``

<img src="http://jcagarcia.github.io/img/gvnix-elements.png" />

<p>Congratulations!!! You have increased the power of your Spring Roo installation!!!!</p>

<h3>Testing advanced functionalities</h3>

<p>Now, you are going to generate a basic <i>petclinic</i> application with bootstrap appearance... remember that this is possible thanks to gvNIX Roo Add-On Suite!</p>

<p><b>1.</b> Open Spring Roo 2.0.0.M1 Shell on an empty directory</p>
<p><b>2.</b> Execute <i>script clinic.roo</i> to generate basic petclinic application</p>
<p><b>3.</b> Execute <i>web mvc jquery setup</i> command provided by gvNIX Roo Add-On Suite to install jQuery in your project.</p>
<p><b>4.</b> Execute <i>web mvc bootstrap setup</i> command provided by gvNIX Roo Add-On Suite to install and use Bootstrap layout.</p>
<p><b>5.</b> Execute <i>exit</i> command to quit Spring Roo Shell</p>
<p><b>6.</b> Run your generated project on Tomcat server. You could use maven command <i>mvn clean compile tomcat:run</i>.</p>

<p>If you follow the steps above, you will have a basic petclinic application with Bootstrap appearance on <a href="http://localhost:8080/petclinic">http://localhost:8080/petclinic</a>:</p>

<img src="http://jcagarcia.github.io/img/petclinic-app.png" />

<p>Enjoy with Roo!</p>
<p><b>Juan Carlos García</b></p>