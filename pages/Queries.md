- Sietske 
  query-table:: false
  Birthday:: [[2025-02-06]]
- query-sort-by:: page
  query-sort-desc:: false
  query-properties:: [:page]
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
- #+BEGIN_QUERY
  {:title "🎂 UPCOMING BIRTHDAYS"
    :query [:find (pull ?h [*])
            :in $ ?start ?next
            :where
            [?h :block/scheduled ?d]
            [?p :block/name "birthday"]
            [?b :block/ref-pages ?p]
            [(mod ?start 10000) ?start-without-year]
            [(mod ?next 10000) ?next-without-year]
            [(mod ?d 10000) ?block-scheduled-without-year]
            [(> ?block-scheduled-without-year ?start-without-year)]
            [(< ?block-scheduled-without-year ?next-without-year)]
            ]
    :inputs [:today :3d-after]
    :collapsed? false}
  #+END_QUERY
	-
- collapsed:: true
  #+BEGIN_QUERY
  
  #+END_QUERY
- query-table:: false
  query-properties:: [:page]
  collapsed:: true
  #+BEGIN_QUERY
  {:title "Citaat"
  :query [:find (pull ?p [*])
       :where
       [?p :block/name ?name]
       [(clojure.string/starts-with? ?name "🇱🇺")]
  ]
  :result-transform (fn [result] [(rand-nth result)] )
  }
  #+END_QUERY
- collapsed:: true
  #+BEGIN_QUERY
  {:title "Block has child"
   :query [:find ?has-child (pull ?b [*])
    :where
     [?b :block/marker "TODO"]
     (or-join [?b ?has-child]
       (and
         [?child :block/uuid ?id]
         [?child :block/parent ?b]
         [(not false) ?has-child]
       )
       (and
         (not
           [?child :block/uuid ?id]
           [?child :block/parent ?b]
         )
         [(not true) ?has-child]
       )
     )
   ]
   :result-transform (fn [r]
     (for [[collapsed, b] (partition 2 r)]
       (assoc b :block/collapsed? collapsed)
     )
   )
  }
  #+END_QUERY
- #+BEGIN_QUERY
  {:title [:b "Alle mooie citaten en teksten"]
    :query [:find (pull ?b [*])
    :where
      [?p :block/original-name "Mooie Citaten en Teksten"]
      [?b :block/page ?p]
    ]
  }
  #+END_QUERY