# Flutter App's simplest automated full test

[![Codemagic build status](https://api.codemagic.io/apps/5ddbe31c011bc93c37050c9f/5ddbe31c011bc93c37050c9e/status_badge.svg)](https://codemagic.io/apps/5ddbe31c011bc93c37050c9f/5ddbe31c011bc93c37050c9e/latest_build)

This project shows an example of the main forms of automated testing in Flutter mobile App, including integration into a [CI/CD platform][], as follows:

- [Unitary][] (including [mocking][] on unitary);
- [Widgets][];
- [Integration][] (or assertion).

Using native libraries or recommended by official Flutter documentation (Google).

> Note that everything here fits within the guidelines set out in [Effective Dart][].

[CI/CD platform]: https://en.wikipedia.org/wiki/CI/CD
[Unitary]: https://flutter.dev/docs/cookbook/testing/unit/introduction
[mocking]: https://flutter.dev/docs/cookbook/testing/unit/mocking
[Widgets]: https://flutter.dev/docs/cookbook/testing/widget/introduction
[Integration]: https://flutter.dev/docs/cookbook/testing/integration/introduction
[Effective Dart]: https://www.dartlang.org/guides/language/effective-dart

## Codemagic - CI for Flutter

At the [Flutter Live][] 2018 conference in London, [Nevercode][] launched their dedicated CI/CD solution for Flutter apps which is known as [Codemagic][].

This project uses **Codemagic for CI/CD**, selected after various analysis and testing with other CI platforms ([Travis CI][], [Codecov][], [Coveralls][]...), which support the Dart language (in some cases only Dart < 2.0), but do not have good support for the Flutter App.

> "Codemagic is the official CI/CD solution dedicated just for Flutter apps."
> \- Getting Started with Codemagic

See more details about Codemagic in '[Getting Started with Codemagic]'.

[Flutter Live]: https://developers.google.com/events/flutter-live/
[Nevercode]: https://nevercode.io/
[Codemagic]: https://codemagic.io/
[Travis CI]: https://travis-ci.org/
[Codecov]: https://codecov.io/
[Coveralls]: https://coveralls.io/
[Getting Started with Codemagic]: https://blog.codemagic.io/getting-started-with-codemagic/

## Prerequisites

You will need [Flutter][] framework 1.9.1+hotfix.6 or above installed.

> The Dart SDK **is not required** because Flutter has _[Dart language][]_ support as an integrated tool in the framework.

[Flutter]: https://flutter.dev/
[Dart language]: https://dart.dev/

**Libraries:**

- [test][] 1.6.3
- [provider][] 3.1.0+1
- [pedantic][] 1.8.0+1 (dev)

[test]: https://pub.dev/packages/test
[provider]: https://pub.dev/packages/provider
[pedantic]: https://pub.dev/packages/pedantic

## Running tests

To test the project, run:

    flutter test

To analyze the Dart language code, run:

    flutter analyze

> The [Dart analyzer][] will check your code and look for possible errors.

[Dart analyzer]: https://flutter.dev/docs/testing/debugging#the-dart-analyzer

To check test coverage, run:

- Run test with `--coverage` flag:

      flutter test --coverage

- Convert the LCOV report generated to a readable HTML file:

      genhtml coverage/lcov.info -o coverage/html

  > The **`flutter test --coverage`** command will generate a **`lcov.info`** file, you will need to install the **[LCOV][]** program to convert (**`genhtml ...`**) the report to an HTML file (human readable).

- Open the HTML report (with a Web Browser)

      google-chrome coverage/html/index.html

[LCOV]: http://ltp.sourceforge.net/coverage/lcov.php

To test only **Unit tests** of the project, run:

    flutter test test/unit/

To test only **Widget tests** of the project, run:

    flutter test test/widget/

To test only **Integration** (or assertion) of the project, run:

    flutter drive --target=test_driver/app.dart

_-->> First, be sure to launch an Android Emulator, iOS Simulator, or connect your computer to a real iOS / Android device. **Integration testing needs to be executed on a real system (simulator or device)!**_

> "Unlike unit and widget tests, integration test suites do not run in the same process as the app being tested. Therefore, create two files that reside in the same directory. By convention, the directory is named **`test_driver`**."
> \- An introduction to integration testing

## Running the APP

To start the mobile App example, run:

    flutter run

## License

Copyright © 2019 | Chinnon Santos | MIT
