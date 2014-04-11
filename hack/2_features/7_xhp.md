!SLIDE 

# XHP #

!SLIDE bullets incremental

* html added to php grammar
* automatically escaped
* valid markup is enforced
* build up markup dynamically
* custom elements
* custom attributes
* define element structure

!SLIDE code

# example

    @@@ php

    $post =
      <div class="post">
        <h2>{$post->title}</h2>
        <p><span>Hello World</span></p>
        <a href={$like_link}>Like</a>
      </div>;

!SLIDE code small

# build up markup dynamically
# gelijk nen DOM

    @@@ php

    $list = <ul />;
    foreach ($items as $item) {
      $list->appendChild(<li>{$item}</li>);
    }

!SLIDE code smaller

# custom elements

    @@@ php

    class :ui:box extends :x:element {
      protected function render() {
        return
          <div class="box">
            <div class="inner">
              {$this->getChildren()}
            </div>
          </div>
      }
    }

    echo 
      <ui:box>Hello World</ui:box>


    // <div class="box">
    //   <div class="inner">
    //    Hello World
    //   </div>
    // </div>

!SLIDE code smaller

# custom attributes

    @@@ php

    class :ui:page extends :x:element {
      attribute
        string title="No Title",
        enum { "post", "page" } type

      protected function render() {
        return
          <div class={$this->getAttribute("type")}>
            <h1>{$this->getAttribute("title")}</h1>
            <div class="body">
              {$this->getChildren()}
            </div>
          </div>
        }
    }

    echo
      <ui:page title="10 things" type="post">
        Lorem Ipsum
      </ui:page>

    // <div class="post">
    //   <h1>10 things</h1>
    //   <div class="body">
    //     Lorem Ipsum
    //   </div>
    // </div>
