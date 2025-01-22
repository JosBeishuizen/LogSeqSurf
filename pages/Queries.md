- {{query (property naam idee)}}
  query-table:: false
  collapsed:: true
- query-table:: true
  #+BEGIN_QUERY
  {:title "🎲"
   :query [:find (pull ?b [*])
     :where 
       [?b :block/page ?p]
       [?b :block/refs ?t]
       [?t :block/name "idee"]
   ]
   :result-transform ( fn [result] [(rand-nth result)] )
  : breadcrumb 
   :collapsed? false
  }
  #+END_QUERY