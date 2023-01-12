

.. _event-system:

************
Event System
************

...

.. _event-system.events:

Events
======

``PHPUnit\Event\TestRunner\Started``

    The test runner was started

``PHPUnit\Event\TestRunner\Configured``

    The test runner was configured.

``PHPUnit\Event\TestRunner\BootstrapFinished``

    The test runner finished executing the configured bootstrap script

``PHPUnit\Event\TestRunner\ExtensionLoadedFromPhar``

    The test runner loaded an extension from a PHP Archive (PHAR)

``PHPUnit\Event\TestRunner\ExtensionBootstrapped``

    The test runner bootstrapped an extension

``PHPUnit\Event\TestSuite\Loaded``

    The test suite was loaded

``PHPUnit\Event\TestSuite\Filtered``

    The test suite was filtered

``PHPUnit\Event\TestSuite\Sorted``

    The test suite was sorted

``PHPUnit\Event\TestRunner\EventFacadeSealed``

    The test runner sealed the event facade

``PHPUnit\Event\TestRunner\ExecutionStarted``

    The test runner started executing tests

``PHPUnit\Event\TestSuite\Started``

    The execution of a test suite was started

``PHPUnit\Event\Test\PreparationStarted``

    The preparation of a test for execution was started

``PHPUnit\Event\Test\BeforeFirstTestMethodCalled``

    A "before first test" method was called for a test case class

``PHPUnit\Event\Test\BeforeFirstTestMethodErrored``

    A "before first test" method errored for a test case class

``PHPUnit\Event\Test\BeforeFirstTestMethodFinished``

    All "before first test" methods were called for a test case class

``PHPUnit\Event\Test\BeforeTestMethodCalled``

    A "before test" method was called for a test method

``PHPUnit\Event\Test\BeforeTestMethodFinished``

    All "before test" methods were called for a test method

``PHPUnit\Event\Test\PreConditionCalled``

    A "precondition" method was called for a test method

``PHPUnit\Event\Test\PreConditionFinished``

    All "precondition" methods were called for a test method

``PHPUnit\Event\Test\TestPrepared``

    A test was prepared for execution

``PHPUnit\Event\Test\ComparatorRegistered``

    A test registered a custom ``Comparator`` for ``assertEquals()``

``PHPUnit\Event\Test\AssertionSucceeded``

    A test successfully asserted something

``PHPUnit\Event\Test\AssertionFailed``

    A test failed to assert something

``PHPUnit\Event\Test\MockObjectCreated``

    A test created a mock object

``PHPUnit\Event\Test\MockObjectForIntersectionOfInterfacesCreated``

    A test created a mock object for an intersection of interfaces

``PHPUnit\Event\Test\MockObjectForTraitCreated``

    A test created a mock object for a trait

``PHPUnit\Event\Test\MockObjectForAbstractClassCreated``

    A test created a mock object for an abstract class

``PHPUnit\Event\Test\MockObjectFromWsdlCreated``

    A test created a mock object from a WSDL file

``PHPUnit\Event\Test\PartialMockObjectCreated``

    A test created a partial mock object

``PHPUnit\Event\Test\TestProxyCreated``

    A test created a test proxy

``PHPUnit\Event\Test\TestStubCreated``

    A test created a test stub

``PHPUnit\Event\Test\TestStubForIntersectionOfInterfacesCreated``

    A test created a test stub for an intersection of interfaces

``PHPUnit\Event\Test\Errored``

    A test errored

``PHPUnit\Event\Test\Failed``

    A test failed

``PHPUnit\Event\Test\Passed``

    A test passed

``PHPUnit\Event\Test\ConsideredRisky``

    A test was considered risky

``PHPUnit\Event\Test\MarkedIncomplete``

    A test was marked incomplete

``PHPUnit\Event\Test\Skipped``

    A test was skipped

``PHPUnit\Event\Test\PhpunitDeprecationTriggered``

    A test triggered a PHPUnit deprecation

``PHPUnit\Event\Test\PhpDeprecationTriggered``

    A test triggered a PHP deprecation

``PHPUnit\Event\Test\DeprecationTriggered``

    A test triggered a deprecation (neither a PHPUnit nor a PHP deprecation)

``PHPUnit\Event\Test\PhpunitErrorTriggered``

    A test triggered a PHPUnit error

``PHPUnit\Event\Test\ErrorTriggered``

    A test triggered an error (not a PHPUnit error)

``PHPUnit\Event\Test\PhpNoticeTriggered``

    A test triggered a PHP notice

``PHPUnit\Event\Test\NoticeTriggered``

    A test triggered a notice (not a PHP notice)

``PHPUnit\Event\Test\PhpunitWarningTriggered``

    A test triggered a PHPUnit warning

``PHPUnit\Event\Test\PhpWarningTriggered``

    A test triggered a PHP warning

``PHPUnit\Event\Test\WarningTriggered``

    A test triggered a warning (neither a PHPUnit nor a PHP warning)

``PHPUnit\Event\Test\Finished``

    The execution of a test method finished

``PHPUnit\Event\Test\PostConditionCalled``

    A "postcondition" method was called for a test method

``PHPUnit\Event\Test\PostConditionFinished``

    All "postcondition" methods were called for a test method

``PHPUnit\Event\Test\AfterTestMethodCalled``

    An "after test" method was called for a test method

``PHPUnit\Event\Test\AfterTestMethodFinished``

    All "after test" methods were called for a test method

``PHPUnit\Event\Test\AfterLastTestMethodCalled``

    An "after last test" method was called for a test case class

``PHPUnit\Event\Test\AfterLastTestMethodFinished``

    All "after last test" methods were called for a test case class

``PHPUnit\Event\TestSuite\Finished``

    The execution of a test suite has finished

``PHPUnit\Event\TestRunner\DeprecationTriggered``

    A deprecation in the test runner was triggered

``PHPUnit\Event\TestRunner\WarningTriggered``

    A warning in the test runner was triggered

``PHPUnit\Event\TestRunner\ExecutionFinished``

    The test runner finished executing tests

``PHPUnit\Event\TestRunner\Finished``

    The test runner has finished

.. _event-system.debugging-phpunit:

Debugging PHPUnit
=================

The test runner's ``--log-events-text`` CLI option can be used to write a plain text representation
for each event to a stream. In the example shown below, we use ``--no-output`` to disable both the
default progress output as well as the default result output. Then we use ``--log-events-text php://stdout``
to write event information to standard output:

.. code-block::
    :caption: todo
    :name: event-system.debugging-phpunit.examples.logging-events

    phpunit --no-output --log-events-text php://stdout
    Test Runner Started (PHPUnit 10.0.0 using PHP 8.2.0 (cli) on Linux)
    Test Runner Configured
    Test Suite Loaded (1 test)
    Test Suite Sorted
    Event Facade Sealed
    Test Runner Execution Started (1 test)
    Test Suite Started (1 test)
    Test Suite Started (default, 1 test)
    Test Suite Started (ExampleTest, 1 test)
    Test Preparation Started (ExampleTest::testOne)
    Test Prepared (ExampleTest::testOne)
    Assertion Failed (Constraint: is true, Value: false)
    Test Failed (ExampleTest::testOne)
    Failed asserting that false is true.
    Test Finished (ExampleTest::testOne)
    Test Suite Finished (ExampleTest, 1 test)
    Test Suite Finished (default, 1 test)
    Test Suite Finished (1 test)
    Test Runner Execution Finished
    Test Runner Finished

Alternatively, the ``--log-events-verbose-text`` CLI option can be used to include information
about resource consumption (time since the test runner was started, time since the previous event,
and memory usage):

.. code-block::
    :caption: todo
    :name: event-system.debugging-phpunit.examples.logging-events-verbose

    phpunit --no-output --log-events-verbose-text php://stdout
    [00:00:00.000035031 / 00:00:00.000004880] [4194304 bytes] Test Runner Started (PHPUnit 10.0.0 using PHP 8.2.0 (cli) on Linux)
    [00:00:00.030921054 / 00:00:00.030886023] [6291456 bytes] Test Runner Configured
    [00:00:00.038802684 / 00:00:00.007881630] [6291456 bytes] Test Suite Loaded (1 test)
    [00:00:00.040860588 / 00:00:00.002057904] [6291456 bytes] Test Suite Sorted
    [00:00:00.042708258 / 00:00:00.001847670] [6291456 bytes] Event Facade Sealed
    [00:00:00.043031136 / 00:00:00.000322878] [6291456 bytes] Test Runner Execution Started (1 test)
    [00:00:00.043277400 / 00:00:00.000246264] [6291456 bytes] Test Suite Started (1 test)
    [00:00:00.043402904 / 00:00:00.000125504] [6291456 bytes] Test Suite Started (default, 1 test)
    [00:00:00.044738027 / 00:00:00.001335123] [6291456 bytes] Test Suite Started (ExampleTest, 1 test)
    [00:00:00.046169639 / 00:00:00.001431612] [6291456 bytes] Test Preparation Started (ExampleTest::testOne)
    [00:00:00.046592057 / 00:00:00.000422418] [6291456 bytes] Test Prepared (ExampleTest::testOne)
    [00:00:00.047769887 / 00:00:00.001177830] [6291456 bytes] Assertion Failed (Constraint: is true, Value: false)
    [00:00:00.051970142 / 00:00:00.004200255] [6291456 bytes] Test Failed (ExampleTest::testOne)
                                                              Failed asserting that false is true.
    [00:00:00.053355327 / 00:00:00.001385185] [6291456 bytes] Test Finished (ExampleTest::testOne)
    [00:00:00.053494019 / 00:00:00.000138692] [6291456 bytes] Test Suite Finished (ExampleTest, 1 test)
    [00:00:00.053557577 / 00:00:00.000063558] [6291456 bytes] Test Suite Finished (default, 1 test)
    [00:00:00.053604485 / 00:00:00.000046908] [6291456 bytes] Test Suite Finished (1 test)
    [00:00:00.053998986 / 00:00:00.000394501] [6291456 bytes] Test Runner Execution Finished
    [00:00:00.054820440 / 00:00:00.000821454] [6291456 bytes] Test Runner Finished

.. _event-system.subscribing-to-events:

Subscribing to Events
=====================

.. code-block:: php
    :caption: todo
    :name: event-system.subscribing-to-events.examples.Extension.php

    <?php declare(strict_types=1);
    namespace Vendor\ExampleExtensionForPhpunit;

    use PHPUnit\Runner\Extension\Extension as PhpunitExtension;
    use PHPUnit\Runner\Extension\Facade as EventFacade;
    use PHPUnit\Runner\Extension\ParameterCollection;
    use PHPUnit\TextUI\Configuration\Configuration;

    final class Extension implements PhpunitExtension
    {
        public function bootstrap(Configuration $configuration, EventFacade $facade, ParameterCollection $parameters): void
        {
            $message = 'the-default-message';

            if ($parameters->has('message')) {
                $message = $parameters->get('message');
            }

            $facade->registerSubscriber(
                new ExecutionFinishedSubscriber(
                    $message
                )
            );
        }
    }

...

.. code-block:: php
    :caption: todo
    :name: event-system.subscribing-to-events.examples.ExecutionFinishedSubscriber.php

    <?php declare(strict_types=1);
    namespace Vendor\ExampleExtensionForPhpunit;

    use const PHP_EOL;
    use PHPUnit\Event\TestRunner\ExecutionFinished;
    use PHPUnit\Event\TestRunner\ExecutionFinishedSubscriber as ExecutionFinishedSubscriberInterface;

    final class ExecutionFinishedSubscriber implements ExecutionFinishedSubscriberInterface
    {
        private readonly string $message;

        public function __construct(string $message)
        {
            $this->message = $message;
        }

        public function notify(ExecutionFinished $event): void
        {
            print __METHOD__ . PHP_EOL . $this->message . PHP_EOL;
        }
    }

...

.. code-block:: xml
    :caption: todo
    :name: event-system.subscribing-to-events.examples.phpunit.xml

    <?xml version="1.0" encoding="UTF-8"?>
    <phpunit xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
             xsi:noNamespaceSchemaLocation="https://schema.phpunit.de/10.0/phpunit.xsd">
        <!-- ... -->

        <extensions>
            <bootstrap class="Vendor\ExampleExtensionForPhpunit\Extension">
                <parameter name="message" value="the-message"/>
            </bootstrap>
        </extensions>

        <!-- ... -->
    </phpunit>

...
