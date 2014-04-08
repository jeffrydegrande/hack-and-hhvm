!SLIDE

# lambdas (that don't suck)

!SLIDE code smaller

    @@@ php
    <?hh

      // basic syntax
      $f = $x ==> $x + 1;
      $f(12); // returns 13;

      
      // quick anonymous functions for array_map
      $squared = array_map($x ==> $x * $x, array(1,2,3));


      // variables are captured automatically (including $this)
      $y = 11;
      $foo = () ==> {
        return $x => $x + $y; // captures $y
      }
      $foo(5); // returns 16


      // or how about something like this
      $captured = "test: ";
      $bar = (string $k = "foo"): string ==> $captured . $k;

      $bar(); // returns "test: foo"
