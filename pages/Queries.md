query-table:: false
#+BEGIN_QUERY
{:title "🎲"
 :query [:find (pull ?b [*])
   :where 
     [?b :block/page ?p]
     [?b :block/refs ?t]
     [?t :block/title "blabla"]
 ]
 :result-transform ( fn [result] [(rand-nth result)] )
 :collapsed? false
}
#+END_QUERY

- ((677d1c77-f603-4313-8ef7-e96973029e4e))
-
-