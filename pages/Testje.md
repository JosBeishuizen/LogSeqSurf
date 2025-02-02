- {{insert-template Quote, }}
- #+BEGIN_QUERY
  {:title "Citaat"
  :query [:find (pull ?b [*])
       :where
       [?b :block/page ?p]
       [?b :block/refs ?t]
       [?t :block/name "☀️"]
  ]
  :result-transform (fn [result] [(rand-nth result)] )
  }
  #+END_QUERY
- #+BEGIN_QUERY
  {:title "Citaat"
  :query [:find (pull ?b [*])
       :where
       [?b :block/page ?p]
       [?b :block/refs ?t]
       [?t :block/name "☀️"]
  ]
  :result-transform (fn [result] [(rand-nth result)] )
  }
  #+END_QUERY
- #+BEGIN_QUERY
  {:title "Citaat"
  :query [:find (pull ?b [*])
       :where
       [?b :block/page ?p]
       [?b :block/refs ?t]
       [?t :block/name "☀️"]
  ]
  :result-transform (fn [result] [(rand-nth result)] )
  }
  #+END_QUERY