query-sort-by:: block
query-table:: true
query-sort-desc:: true
query-properties:: [:block]
#+BEGIN_QUERY
{:title "🎲"
 :query [:find (pull ?b [*])
   :where 
     [?b :block/page ?p]
     [?b :block/refs ?t]
     [?t :block/name "tag1"]
 ]
 :result-transform ( fn [result] [(rand-nth result)] )
 :collapsed? true
}
#+END_QUERY

-