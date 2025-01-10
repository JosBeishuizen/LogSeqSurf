query-sort-by:: block
query-table:: false
query-sort-desc:: true
query-properties:: [:block]
#+BEGIN_QUERY
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
#+END_QUERY

- :
-
-