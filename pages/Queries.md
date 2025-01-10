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
 :collapsed? true
}
#+END_QUERY

- Een goede gedachte
  id:: 6780f000-9bb5-4704-b903-80a5f68fac87
  name:: ☀️
- name:: ☀️
  Een tweede goede gedachte
- name:: ☀️
  Een derde goede gedachte
-