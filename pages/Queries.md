query-table:: false

- query-sort-by:: page
  query-sort-desc:: false
  query-properties:: [:page]
  collapsed:: true
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
- {:title "🎂 Birthday"
    :query [:find (pull ?b [*])
      :in $ ?today
      :where
         [?b :block/properties-text-values ?props]
         [(get ?props :birthday) ?birthday]
         
         [(str ?birthday) ?birthdayString]
         [(subs ?birthdayString 7 9) ?month]
         [(subs ?birthdayString 10 12) ?day]
  
         [(str ?today) ?td]
         [(subs ?td 4 6) ?todayMonth]
         [(subs ?td 6 8) ?todayDay]
  
         [(= ?month ?todayMonth)]
         [(= ?day ?todayDay)]
         
  ]
  :inputs [:today]
  :collapsed? false}
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