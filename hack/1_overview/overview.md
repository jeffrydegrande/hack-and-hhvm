!SLIDE subsection

# Hack & HHVM

!SLIDE bullets

# HipHop #

* PHP => C++
* FAST
* slow development cycle

!SLIDE bullets

# HHVM #

* JIT compiler + VM
* runs PHP
* php modules (the important ones) are available (curl, mysqli, ..)

!SLIDE bullets incremental

# performance #

* Supposed to be fast
* 300% improvement vs 5.3
* 200% improvement vs 5.5
* One dude reported having benchmarked his code at 5x original speed

!SLIDE bullets smaller

# Hack #

* language on top of HHVM
* interoperates seamlessly with PHP
* cleaner, safer & refactorable code
* annotate code + tool to validate those annotations
* lots and lots of cool features
* type checking is done **before** runtime and is **not** enforced at runtime.
