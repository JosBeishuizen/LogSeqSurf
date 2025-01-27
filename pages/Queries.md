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
- #+BEGIN_QUERY 
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
-
-