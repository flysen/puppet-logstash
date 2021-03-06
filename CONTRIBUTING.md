# Contributing

If you have a bugfix or new feature that you would like to contribute to this puppet module, please find or open an issue about it first. Talk about what you would like to do. It may be that somebody is already working on it, or that there are particular issues that you should know about before implementing the change.

We enjoy working with contributors to get their code accepted. There are many approaches to fixing a problem and it is important to find the best approach before writing too much code.

The process for contributing to any of the Elasticsearch repositories is similar.

1. Sign the contributor license agreement  
Please make sure you have signed the [Contributor License Agreement](http://www.elasticsearch.org/contributor-agreement/). We are not asking you to assign copyright to us, but to give us the right to distribute your code without restriction. We ask this of all contributors in order to assure our users of the origin and continuing existence of the code. You only need to sign the CLA once.

2. Run the rspec tests and ensure it completes without errors with your changes.

3. Rebase your changes
Update your local repository with the most recent code from the main this puppet module repository, and rebase your branch on top of the latest master branch. We prefer your changes to be squashed into a single commit.

4. Submit a pull request
Push your local changes to your forked copy of the repository and submit a pull request. In the pull request, describe what your changes do and mention the number of the issue where discussion has taken place, eg “Closes #123″.

Then sit back and wait. There will probably be discussion about the pull request and, if any changes are needed, we would love to work with you to get your pull request merged into this puppet module.


## Development Setup

There are a few testing prerequisites to meet:

* Ruby
* [Bundler](http://bundler.io/)
* Puppet (You should be able to run `puppet module install`
* Docker or Vagrant/Virtualbox for the acceptance tests

You can then set up the test enviroment with:
```bash
make
```

## Testing

### Unit Tests
Run the unit tests with:

```
make test-unit
```

## Acceptance Tests
Acceptance tests are implemented with Beaker, RSpec and Serverspec.

You can run them for a particular operating system and a particular Logstash version like this:

```
BEAKER_set=debian-8 LOGSTASH_VERSION=1.4.5 bundle exec rake beaker
```

That invocation requires that you have Docker installed on your development system.
If you'd prefer to use Vagrant and Virtualbox, you can:

```
BEAKER_set=debian-8-vagrant LOGSTASH_VERSION=1.4.5 bundle exec rake beaker
```
