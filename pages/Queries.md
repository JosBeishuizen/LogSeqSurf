- {{query (tags "🇱🇺")}}
  query-table:: false
  collapsed:: true
- query-table:: false
  #+BEGIN_QUERY
  {:title "☀️"
   :query [:find (pull ?b [*])
     :where 
           [?p :block/name ?name]
           [(clojure.string/starts-with? ?name "🇱🇺")]
   ]
   :result-transform ( fn [result] [(rand-nth result)] )
  :breadcrumb-show? true
   :collapsed? false
  }
  #+END_QUERY
-
- query-sort-by:: page
  query-sort-desc:: false
  collapsed:: true
  #+BEGIN_QUERY
  {:title "Pages that start with 🇱🇺"
   :query [:find (pull ?p [*])
           :where 
           [?p :block/name ?name]
           [(clojure.string/starts-with? ?name "🇱🇺")]]
  }
  #+END_QUERY