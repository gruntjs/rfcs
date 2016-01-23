# Grunt RFCs

> Inspired by the [Ember.js RFC process] and [Rust RFC process].

Many changes, including bug fixes and documentation improvements can be
implemented and reviewed via the normal GitHub pull request workflow.

Some changes though are "substantial", and we ask that these be put through a
bit of a design process and produce a consensus among the Grunt core team.

The "RFC" (request for comments) process is intended to provide a consistent
and controlled path for new features to enter the codebase.

## Active RFC List

* None at this time.

## When you need to follow this process

You need to follow this process if you intend to make "substantial" changes to
Grunt. What constitutes a "substantial" change is evolving based on community
norms, but may include the following.

  - Any new feature that creates new API surface area.
  - Removing features that already shipped as part of the release channel.
  - The discretion of a Grunt core team member.

Some changes do not require an RFC:

  - Rephrasing, reorganizing or refactoring.
  - Additions that strictly improve objective, numerical quality
  criteria (speedup, better support).
  - The discretion of a Grunt core team member.

If you submit a pull request to implement a new feature without going
through the RFC process, it may be closed with a polite request to
submit an RFC first.

## Gathering feedback before submitting

It's often helpful to get feedback on your concept before diving into the
level of API design detail required for an RFC. You can always open an
issue on this repo to open up high-level discussion, with the goal of
eventually formulating an RFC pull request with the specific implementation
design.

## What the process is

In short, to get a major feature added to Grunt, one must first get the
RFC merged into the RFC repo as a markdown file. At that point the RFC
is 'active' and may be implemented with the goal of eventual inclusion
into Grunt.

* Fork the RFC repo http://github.com/gruntjs/rfcs
* Copy `0000-template.md` to `text/0000-my-feature.md` (where
'my-feature' is descriptive. don't assign an RFC number yet).
* Fill in the RFC. Put care into the details: RFCs that do not
present convincing motivation, demonstrate understanding of the
impact of the design, or are disingenuous about the drawbacks or
alternatives tend to be poorly-received.
* Submit a pull request. As a pull request the RFC will receive design
feedback from the larger community, and the author should be prepared
to revise it in response.
* Build consensus and integrate feedback. RFCs that have broad support
are much more likely to make progress than those that don't receive any
comments.
* Eventually, somebody on the core team will either accept the RFC by
merging the pull request and assigning the RFC a number, at which point
the RFC is 'active', or reject it by closing the pull request.

## The RFC life-cycle

Once an RFC becomes active then authors may implement it and submit the
feature as a pull request to the Grunt repo. An 'active' is not a rubber
stamp, and in particular still does not mean the feature will ultimately
be merged; it does mean that the core team has agreed to it in principle
and are amenable to merging it.

Furthermore, the fact that a given RFC has been accepted and is
'active' implies nothing about what priority is assigned to its
implementation, nor whether anybody is currently working on it.

Modifications to active RFC's can be done in followup PR's. We strive
to write each RFC in a manner that it will reflect the final design of
the feature; but the nature of the process means that we cannot expect
every merged RFC to actually reflect what the end result will be at
the time of the next major release; therefore we try to keep each RFC
document somewhat in sync with the language feature as planned,
tracking such changes via followup pull requests to the document.

An RFC that makes it through the entire process to implementation is
considered 'complete' and is moved to the 'complete' folder; an RFC
that fails after becoming active is 'inactive' and moves to the
'inactive' folder.

## Implementing an RFC

The author of an RFC is not obligated to implement it. Of course, the
RFC author (like any other developer) is welcome to post an
implementation for review after the RFC has been accepted.

If you are interested in working on the implementation for an 'active'
RFC, but cannot determine if someone else is already working on it,
feel free to ask (e.g. by leaving a comment on the associated issue).

[Ember.js RFC process]: https://github.com/emberjs/rfcs
[Rust RFC process]: https://github.com/rust-lang/rfcs
