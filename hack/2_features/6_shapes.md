!SLIDE

# Shapes #

type-checkable, struct-like entities so plain arrays aren't used for this
purpose

!SLIDE code small

    @@@ php
    <?hh

      type Point2D = shape('x' => int, 'y' => int);

      function dotProduct(Point2D $a, Point2D $b): int {
        return $a['x'] * $b['x'] + $a['y'] * $b['y'];
      }

      dotProduct(shape('x' => 3, 'y' => 3),
                 shape('x' => 4, 'y' => 4));

      // so funky stuff like this won't be allowed to pass 
      // the type checker and kill puppies

      dotProduct(array('x' => 'foo', 'y' => 'foo'),
                 array('x' => 'baz', 'y' => 'baz'));

      // can be used with generics
      type Point<T> = shape('x' => T, 'y' => T);

      shape('x' => 1.0, 'y' => 2.0);
      shape('x' => 1, 'y' => 2);
