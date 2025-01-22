- {{query (property naam idee)}}
  query-table:: false
  collapsed:: true
- {:title "🎲"
   :query [:find (pull ?b [*])
     :where 
       [?b :block/page ?p]
       [?b :block/refs ?t]
       (or
         [?t :block/name "tag1"]
         [?t :block/name "tag2"]
       )
   ]
   :result-transform ( fn [result] [(rand-nth result)] )
   :collapsed? true
  }