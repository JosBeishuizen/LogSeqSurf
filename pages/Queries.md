query-table:: false

- query-sort-by:: page
  query-sort-desc:: false
  query-properties:: [:page]
  collapsed:: true
  #+BEGIN_QUERY
  {:title "Pages that start with 🇱🇺"
   :query [:find (pull ?p [*])
           :where 
           [?p :block/name ?name]
           [(clojure.string/starts-with? ?name "🇱🇺")]]
  :table-view? false
  :breadcrumb-show? false
  :collapsed? false
  }
  #+END_QUERY
-
- query-table:: false
  query-properties:: [:page]
  #+BEGIN_QUERY
  {:title "Citaat"
  :query [:find (pull ?p [*])
       :where
       [?p :block/name ?name]
       [(clojure.string/starts-with? ?name "🇱🇺")]
  ]
  :result-transform (fn [result] [(rand-nth result)] )
  }
  #+END_QUERY
- collapsed:: true
  #+BEGIN_QUERY 
  {:title "Citaat"
   :query [:find (pull ?b [*])
     :where 
       [?b :block/page ?p]
       [?b :block/refs ?t]
       [?t :block/name "☀️"]
   ]
   :result-transform ( fn [result] [(rand-nth result)] )
   :collapsed? true
  }
  #+END_QUERY
-
- #+BEGIN_QUERY
  {:title "Block has child"
   :query [:find ?has-child (pull ?b [*])
    :where
     [?b :block/marker "TODO"]
     (or-join [?b ?has-child]
       (and
         [?child :block/uuid ?id]
         [?child :block/parent ?b]
         [(not false) ?has-child]
       )
       (and
         (not
           [?child :block/uuid ?id]
           [?child :block/parent ?b]
         )
         [(not true) ?has-child]
       )
     )
   ]
   :result-transform (fn [r]
     (for [[collapsed, b] (partition 2 r)]
       (assoc b :block/collapsed? collapsed)
     )
   )
  }
  #+END_QUERY
-