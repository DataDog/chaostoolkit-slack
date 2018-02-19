# Chaos Toolkit Extension for Slack

This project is an extension for the Chaos Toolkit to target [Slack][slack].

[slack]: https://slack.com/

## Install

This package requires Python 3.5+

To be used from your experiment, this package must be installed in the Python
environment where [chaostoolkit][] already lives.

[chaostoolkit]: https://github.com/chaostoolkit/chaostoolkit

```
$ pip install -U chaostoolkit-slack
```

## Usage

Currently, this extension only provides notification support to send Chaos
Toolkit events to Slack channels.

To use this extension, edit your `chaostoolkit` settings by adding the
following payload:

```yaml
notifications:
  -
    type: plugin
    module: chaosslack.notification
    token: xop-1235
    channel: general
```

By default all events will be forwarded to that channel. You may filter only
those events you care for:


```yaml
notifications:
  -
    type: plugin
    module: chaosslack.notification
    token: xop-1235
    channel: general
    events:
      - run-failed
      - run-started
```

Only sends those two events.

## Test

To run the tests for the project execute the following:

```
$ pytest
```

## Contribute

If you wish to contribute more functions to this package, you are more than
welcome to do so. Please, fork this project, make your changes following the
usual [PEP 8][pep8] code style, sprinkling with tests and submit a PR for
review.

[pep8]: https://pycodestyle.readthedocs.io/en/latest/

The Chaos Toolkit projects require all contributors must sign a
[Developer Certificate of Origin][dco] on each commit they would like to merge
into the master branch of the repository. Please, make sure you can abide by
the rules of the DCO before submitting a PR.

[dco]: https://github.com/probot/dco#how-it-works