query-table:: true
#+BEGIN_QUERY
{:title "🎲"
 :query [:find (pull ?b [*])
   :where 
     [?b :block/page ?p]
     [?b :block/refs ?t]
     [?t :block/name "idea"]
 ]
 :result-transform ( fn [result] [(rand-nth result)] )
 :collapsed? true
}
#+END_QUERY

- ((☀️))
-