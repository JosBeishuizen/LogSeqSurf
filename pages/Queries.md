- {{query (tags "🇱🇺")}}
  query-table:: false
	- query-sort-by:: page
	  query-table:: false
	  query-sort-desc:: false
	  #+BEGIN_QUERY
	  {:title "☀️"
	   :query [:find (pull ?p [*])
	     :where 
	           [?p :block/name ?name]
	           [(clojure.string/starts-with? ?name "🇱🇺")]
	   ]
	   :result-transform ( fn [result] [(rand-nth result)]
	  :table-view? false 
	  :breadcrumb-show? false
	   :collapsed? false
	  }
	  #+END_QUERY
- query-sort-by:: page
  query-sort-desc:: true
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