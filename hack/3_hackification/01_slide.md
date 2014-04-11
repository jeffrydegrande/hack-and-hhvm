!SLIDE subsection

# Hackification #

!SLIDE code

# Hack Modes

    @@@ php

    <?hh // strict
    
    <?hh // partial
    <?hh

    <?hh // decl

    // UNSAFE

!SLIDE code smaller

# STEP 1: run hackificator script

    @@@ php

    <?php
    class Person {
      private $name;

      function __construct($name = null) {
        $this->name = $name;
      }
    }

    function main() {
      $person = new Person("Jeffry");
    }

    //
    // after running $ hackificator .
    //

    <?hh 
    class Person {
      private $name;

      function __construct($name = null) {
        $this->name = $name;
      }
    }

    function main() {
      $person = new Person("Jeffry");
    }

!SLIDE bullets small

# hackificator does a few more small things

* adding nullables where needed
* adding empty parameter list on constructors. i.e. new Thing => new Thing()


!SLIDE code smaller

# STEP 2: inferring type annotations
# aka soft type annotations

    @@@ php

    // after running $ hh_server --convert <dir> <rootdir>

    <?hh 

      class Person {
        private ?string $name;

        public function __construct(@?string $name = null) {
          $this->name = $name;
        }
      }

      function main(): @void {
        $person = new Person("Jeffry");
      }


!SLIDE bullets small

* soft types are self-consistent and don't cause type errors
* they may be wrong
* @T is kind of like PHP's error suppression.
* No hard failure but errors do get logged

!SLIDE bullets small

* STEP 3 (final): "hardening" type annotations 
* `hack_remove_soft_types --harden`
* has a --delete-from-log
* annotations are now hard failures
