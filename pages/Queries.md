- #+BEGIN_QUERY
  query-sort-by:: block
  query-table:: false
  query-sort-desc:: true
  query-properties:: [:block]
  {:title "🎲"
   :query [:find (pull ?b [*])
     :where 
       [?b :block/page ?p]
       [?b :block/refs ?t]
       [?t :block/name "☀️"]
   ]
   :result-transform ( fn [result] [(rand-nth result)] )
   :collapsed? false
  }
  #+END_QUER
- ((677d1c79-9ad1-4d51-be3f-17c88703eac9))
-
-