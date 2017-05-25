Testing
########

1. Acceptance Test for running one function
--------------------------------------------

.. code-block:: php

    php vendor/codeception/codeception/codecept run acceptance TrackDetail/User/TrackDetailCest::testCase001 --env local-phantomjs --debug


2. Acceptance Test for multiple groups
---------------------------------------

  * Multi group

    .. code-block:: php

        ... -g admin -g editor

    * Ref: http://codeception.com/docs/07-AdvancedUsage


  * For one group

    .. code-block:: php

        php vendor/codeception/codeception/codecept run acceptance TrackSearch --env aws-vn --group delivery-setting --debug
