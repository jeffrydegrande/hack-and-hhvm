!SLIDE

# Collections #

!SLIDE bullets

* Vector
* Map
* Set
* Pair
* Tuple

!SLIDE code small

# Vector

    @@@ php

    <?hh

      $vec = Vector {1,2,3,4};

      $vec[] = 20;
      echo $vec[0];
      foreach($map as $value) {}
      foreach($map as $key => $value) {}
      $vec->filter($x ==> $x >= 50);
      $vec->map( $x ==> $x * 2 );

!SLIDE code small 

# Map

    @@@ php

    <?hh

      $map = Map { "A" => 1, "B" => 2 }
      $map["D"] => 4;

      $map->contains("B");
      $map->get("B");
      $map->remove("B");
      foreach($map as $value) {}
      foreach($map as $key => $value)

!SLIDE bullets

* Set
* Pair
* Tuple
* Immutable versions ImmVector, ImmMap, ImmSet
