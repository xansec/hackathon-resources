# Hackathon Resources

## Useful Links

- [Mayhem Online GUI](https://mayhem.forallsecure.com/)

- [Mayhem Documentation](https://mayhem.forallsecure.com/docs/)

- [Mayhem Community](https://community.forallsecure.com/)

- [Discord Invite](https://discord.gg/UNBvxyq6)

- [Survey](https://dydbdnwi0qu.typeform.com/to/jZEKf0it)

## Exercises

1. [lighttpd exercise](lighttpd-example.md)
2. [Docker + Mayhem Exercise](docker-intro.md)
3. [CMake Exercise](cmake-libfuzzer-exercise.md#cmake-exercise)
4. [libFuzzer Exercise](cmake-libfuzzer-exercise.md#libfuzzer-exercise)
5. [Mayhem GitHub Action Exercise](gh-actions.md)

## Mayhem Heroes Workflow

1. Select a repository for integration.

    See the target requirements for more information on what qualifies for integration.

2. Create a fork of the repo you want to integrate.

3. Integrate Mayhem into your Fork.

4. Submit [this form](https://dydbdnwi0qu.typeform.com/to/l6MK0WJp).

5. Once ForAllSecure validates your target and elligiblity, you'll be asked to submit a pull request to the repository under github.com/mayhemheroes. If requested during the review, make changes.

6. Once your changes have been merged, you'll be eligible to get paid!
    * $100 for integration
    * $200 if the number of tests per second is greater than 100
    * $200 if the test suite size is greater than 100
    * $200 if a new function harness is added
    * $300 if defect(s) are discovered

## Target Checklist

Targets that you wish to get paid for must meet the following criteria:

* Is a public repository on github.com.  Private repositories are currently not qualified.

* Has 100 or more stars.

* All code is open source and available in source code format.

    - Code is considered Open Source if the entire code base is licensed under one (or more) of [the recognized Open Source Initiative Licenses](https://opensource.org/licenses/alphabetical). 

* Mayhem is not already integrated; you can find a list of integrated repositories [here](https://github.com/mayhemheroes).

* The project is not already a part of OSS-Fuzz; you can find a list of integrated repositories [here](https://github.com/google/oss-fuzz/tree/master/projects).

* The project has been active in the last 6 months.

* The resulting Mayhem run generates > 10 new test cases.

* The target isn't inappropriate (e.g. an integration of [fetlang (NSFW)](https://github.com/fetlang/fetlang) was submitted and, despite meeting the criteria above, was rejected).

If in doubt, ask in Discord or on the Mayhem Community.

_ForAllSecure reserves the right to reject any submission at its sole discretion._

## Troubleshooting Checklist

There are several small configuration steps that you'll need to take on your repo in order to properly integrate a repo with Mayhem. They are easy to miss, so here is a list for your reference:

* Package has public visibility.

* Fork repository is configured with a `MAYHEM_TOKEN` secret.

