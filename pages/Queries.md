- {{query (tags "🇱🇺")}}
  query-table:: false
	- query-sort-by:: page
	  query-table:: false
	  query-sort-desc:: false
	  collapsed:: true
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
		- collapsed:: true
		  #+BEGIN_QUERY 
		  {:title "Citaat"
		   :query [:find (pull ?b [*])
		     :where
		       [?b :block/name ?name]
		       [clojure.string/starts-with? ?name "🇱🇺")]
		   ]
		   :result-transform ( fn [result] [(rand-nth result)] )
		   :collapsed? true
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