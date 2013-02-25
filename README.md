CacheBundle
===========

A fluent cache bundle for Symfony 2.

Installation
======

  composer require phpfluent/cachebundle

Update the settings.yml file

  services:
      cache:
          class: Doctrine\Common\Cache\ApcCache

Register the bundle

  %/app/AppKernel.php
  <?php

  $bundles = array(
	new Symfony\Bundle\FrameworkBundle\FrameworkBundle(),
	new Symfony\Bundle\TwigBundle\TwigBundle(),
	new Symfony\Bundle\MonologBundle\MonologBundle(),
	new Symfony\Bundle\SwiftmailerBundle\SwiftmailerBundle(),
	/**
	 * Your bundles
	 */
	new PHPFluent\Bundle\CacheBundle\CacheBundle(),
  );

Call it from your code

  $cache = $this->get('phpfluent_cache');

  $cache['foo'] = 'bar'; //Caching
  echo $cache['foo'];//Retrieving from the cache