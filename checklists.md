# Checklists for Better Software

These are lecture notes for [Checklists For Better Software](https://youtube.com/watch?v=B9pulMZwUUY) by D. Richard Hipp, held in 2013 in the SouthEast Linux Fest in Charlotte, North Carolina. The lecture has been made available under
the [Creative Commons Attribution 3.0 Unported](https://creativecommons.org/licenses/by/3.0/legalcode) license.

## Motivation

* 35-50% fewer defects
* 50% greater team cohesion
* 20% increase in job satisfaction
* 3x reduction in annual staff turnover
* Faster release cycles
* Reduced stress and workload
* Source: Gawande, A. (2011). *The Checklist Manifesto: How to Get Things Right.* London: Profile Books.

## Techniques for Reliable Software

* Careful and robust design
* Detailed documentation
* Good test coverage
* Checklists can make a huge difference in quality

## Checklists in Flying

* Checklists has become the standard way of flying airplanes.
* They take a lot of mental load off of flying.
* "I'm smart, I don't need checklists"
  * Checklists are actually designed for smart people
  * Focuses effort on executing the steps rather than trying to remember them

## Good and Bad Checklists

* Use "good" checklists
* A "bad" checklist is worse than no checklist at all

## Bad Checklists

* Verbose
* Vague or imprecise
* Imposed by management fiat
  * People have to really believe checklists are helping them, otherwise
    it is not going to be working for them.
* Written like an instruction manual
  * The checklist should be just an outline, the "title page".
* Resented by users
* Turns people into mindless robots
  * The checklist is supposed to focus you, engage you, and make you more productive.
* Untested
  * If it has not been tested, it does not work.

## Good Checklists

* Precise, succinct, and efficient
* Touches the most critical steps
* Targets highly skilled professionals
* Written by end users
  * The people who use the checklist should be involved in writing it.
* Encourages a culture of teamwork and discipline
* Helps people work smarter and faster
* Continuously refined

## Checklist wisdom

* A checklist cannot fix incompetence
* A checklist is just a guide to help you along
* Two types of checklists:
  1. Critical steps that must not be overlooked
     * Are you working on the right patient?
     * Are you doing the correct procedure?
     * Are we sure it's the left leg we're supposed to amputate and not the right?
  2. Team building
     * For example: confirm that all team members have introduced themselves by name and role
     * Designed to encourage teamwork
     * Helps communication by making team members talk to each other
     * Makes teamwork more efficient

## Apollo 8 Launch

* Seemingly pointless dialogue between flight crew and command center
* Everything during staging happens automatically, but the flight crew asks
  for if everything is ready for staging?!
* Maybe the purpose is to get everybody talking, so that if something goes
  wrong, everybody is prepared.

## Examples of Checklists in Software Development

* Checkin/commit checklist
* Unit test
* Release test
* Bug response
* New feature
* Design rules
* Pre- and post-peer review

## SQLite pre-checkin checklist

* `fossil diff` → no stray changes
* `fossil extra` → no unmanaged files
* checkin will go to the intended branch
* auto-sync is on, or system time verified
* if files added/removed → makefiles updated
* no compiler warnings (trunk checkin only)
* at least one test suite run and passed (trunk check-in only)

## Keeping Checklists Concise

* The checklist should be something like an A4 sized short piece of document
* Unfamiliar items like "no stray changes" can have more in-depth
  explanations in a separate document, e.g. to make onboarding smoother

## Status Boards

* In SQLite they use an interactive page that shows status of different checklists for a given release
* "You ought to be automating all of these tests"
  * Each checklist item corresponds to a big test suite that runs hundreds of tests, sometimes for hours
  * Each checklist item is run manually step-by-step, to keep a human in the loop

## Keeping a Human in the Loop

* Having checklists does not mean they cannot be automated
* However, when there's a human in the loop, you'll sometimes spot things that automatic tests don't see
* Sometimes when you dig deeper, you'll find problems even though the test technically passed
* Test automations are a really good thing, and some of the checklists may
  contain tens of thousands of test cases that run automatically
* But you still want a human to evaluate things from time to time
* The release checklist has multiple people working on it and may take
  a couple of days
* When the whole thing goes green, we're ready to release

## Bug Response Checklist

* Write a ticket
* Bisect → Identify affected releases
* Notify key customers
* Add test cases that demonstrate the bug
* Fix the bug
* All-developer meeting:
  * Procedure changes that would have prevented this issue and/or similar issues
  * Similat issues elsewhere in the code?

## New Feature Checklist

* Complies with design rules (peer review)
* Handles OOM errors (review & tests)
* Handles I/O errors (review & tests)
* Threadsafe (review & `assert()`)
* Works for all page sizes (tests)
* Boundary values tested (`testcase()` macros)
* Documentation complete & correct (review)
* ...Plus 17 other checks

## Checklist for Software Checklists

* Precise → specifics, not vague generalities
* Concises → separate details if required
* Editable → probably on a wiki
* Low-ceremony
* Written by the people who use it
* Checks the most critical steps
* Encourages teamwork and collaboration

## Checklist Wisdom

* "Plans are nothing; planning is everything" —Eisenhower
* The very process of making a checklist forces you to think about
  your processes and how you develop software.
* Just going through the exercise of writing the checklist will help
  you to write better software, even if you never end up using that
  checklist.
* Because you've spent time thinking about how is it that we are going
  about doing our work.

## Checklists and Teamwork

* As projects grow, one of the problems is people not communicating
* The magic number for chaos is about 12 developers
  * When you get more than ~12 developers, communication becomes a big deal
* You've got to keep everybody talking and on the same page
* Checklists are a big help
* But checklists are not a silver bullet

## Checklists and Automation

* There seems to be tension between automation and doing stuff manually
* "That's a huge checklist, why don't you automate that?"
* In SQLite they *have* automated a lot of it
* Each checklist item is huge amount of automation
* But why don't we just do one more level of automation on top of it
  and have a single checklist item that says "We ran the release test
  and it worked".
* There's a trade-off there and it's hard to balance it
* Having a human in the loop helps you to spot things that aren't really
  part of the checklist
* The automation won't necessary spot all the errors
* If there's a human reviewing it, the human will sometimes spot things
  that you didn't even think to look at before
* There is some tension: how much should you automate versus how much you
  should keep the human in the loop
  * There's no perfect answer
* Sometimes you can't automate until you have a checklist to automate
* If you want to automate something:
  1. Write a checklist
  2. Run the checklist a few times manually to make sure it actually works
  3. Try to automate it
* Some things are not automatable:
  * Code reviews
  * Some hardware
