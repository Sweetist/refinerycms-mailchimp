[![Build Status](https://secure.travis-ci.org/Wirelab/refinerycms-mailchimp.png?branch=feature/2.0.0)](http://travis-ci.org/Wirelab/refinerycms-mailchimp)

# Mailchimp engine for Refinery CMS

This project was originally sponsored by Mailchimp and is now maintained and funded by [Wirelab Creative](http://www.wirelab.nl)!  Many thanks to them for supporting open source development.

## How to use this engine with a Refinery CMS project

To set up a Refinery app from scratch, you'll need to install Refinery and create a new app:

    gem install refinerycms
    refinerycms new_project
    cd new_project

Once you have a Refinery app created, add this engine to your Gemfile in the `USER DEFINED` area:

    gem 'refinerycms-mailchimp', :github => 'Wirelab/refinerycms-mailchimp', :branch => 'feature/2.0.0'

Then, from the command line:

    bundle install
    rails generate refinery:mailchimp
    rake db:migrate

## Settings

You'll need to set up your Mailchimp API key in `config/initializers/refinery/mailchimp.rb`. [Get your API key here.](https://admin.mailchimp.com/account/api-key-popup)

All available settings are:

* `mailchimp_default_to_name`  The default To: name recipients will see (not email address). This can be changed for each campaign.
* `mailchimp_default_from_name`  The default From: name for your campaign message (not an email address). This can be changed for each campaign.
* `mailchimp_default_from_email`  The default From: email address for your campaign message. This can be changed for each campaign.

## Using Templates

This plugin currently only supports one editable text area per campaign.  If you use a template, the body will replace the template's MAIN area (see [the Mailchimp docs on editable content areas](http://kb.mailchimp.com/article/template-language-creating-editable-content-areas)).

## How to run the test suite

Uncomment the following line in your Gemfile:

    gem 'refinerycms-testing',    '~> 0.9.9.9'

Then install the testing functionality with

    rails generate refinerycms_testing

You can now run all engine specs and features with `rake`, or run them separately with `rake spec` and `rake cucumber`.
