!SLIDE 

# Type Annotations

!SLIDE code

# php
  
    @@@ php 
    // PHP
    function getAge($person) {
      return $person->getAge();
    }

    getAge(null); // BOOM in production
    getAge(true); // BOOM in production
    getAge(new Person()); // :)

!SLIDE code small

# slightly better

    @@@ php 
    // PHP
    function getAge(Person $person) {}

    // ... but what about primitive types?
    function convertToMetric(float $pound) {}

    // type hints for scalar types were implemented around May 2010, 
    // but never made it into 5.4.
    // "against fundamental design of PHP". Meh

!SLIDE code

    @@@ php

    // HACK
    function getAge( Person $person ): int {
      return $person->getAge();
    }

    getAge(null) => type checker complains 
    getAge(true) => type checker complains
    getAge(new Person()) => :) 

!SLIDE code small

# Nullable types

    @@@ php

    function getAge(?Person $person): int {
      if (is_null($person)) {
        throw new Exceptionl("Unexpected null");
      }
      return $person->getAge();
    }

    getAge(null) => throws exception
    getAge(true) => type checker complains
    getAge(new Person()) => :)
