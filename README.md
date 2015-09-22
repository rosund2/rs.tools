
# Lein and local profile
Ensuring the projects use the same repl as cider in emacs
and adding the vinyasa plugin to ensure that i can switch namespaces without requiering
pprint and doc/source utilities everywere

*Add this snippit to .lein/profile.clj*
``` clojure
{:user {:plugins [[cider/cider-nrepl "0.9.1"]]
        :dependencies [[im.chit/vinyasa "0.1.8"]]
        :inections [(require 'vinyasa.inject)
                    (vinyasa.inject/inject 'clojure.core '>
                                           '[[clojure.repl doc source]
                                             [clojure.pprint pprint pp]])]}}

```

