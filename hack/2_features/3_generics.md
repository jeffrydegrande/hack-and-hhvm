!SLIDE

# Generics #

!SLIDE code small

    @@@ php

    <?hh

      class Box<T> {
        protected T $data;

        public function __construct(T $data) {
          $this->data = $data;
        }

        public function getData(): T {
          return $this->data;
        }
      }

      new Box(3);
      new Box("Hello");
      new Box(array());

!SLIDE

use case: Generic code can be checked statically instead of relying on instanceof
& friends.
