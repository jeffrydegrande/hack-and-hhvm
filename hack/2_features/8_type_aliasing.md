!SLIDE code smaller

# Type aliasing

    @@@ php
    <?hh

    // normal type aliasing
    type MyInt = int;
    function foo(MyInt $mi): void {}

    // opaque type aliasing, difference is that only the 
    // the file where the type is defined is allowed to access
    // the underlying implementation. (i.e. operate on int)

    newtype MyInt = int;
    function foo(MyInt $mi): void {}

    // will type check in same file, but not from another file. HHVM
    // will run it though
    foo(1234);

!SLIDE code smaller

# more useful example

    @@@ php

    // in time.php
    <?hh
      newtype TIMESTAMP_IN_UTC = int;

      function time_in_utc(): TIMESTAMP_IN_UTC {
        return time();
      }

      function in_local_tz(TIMESTAMP_IN_UTC $timestamp): int {
        $offset = blahblah();
        return $timestamp - $offset;
      }


    // somewhere else
    <?hh
      require 'time.php';

      in_local_tz(time()); // typechecker complains
      in_local_tz(123); // here too
      
      in_local_tz(time_in_utc()); // works
