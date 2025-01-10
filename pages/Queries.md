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
  De grazige weiden de rustige wateren  
  op het behang van mijn kamer  
  ik heb geloofd als een bang kind  
  in behang  
  
  als mijn moeder voor mij gebeden  
  had en mij weer eens een dag langer  
  vergeven was bleef ik achter  
  tussen roerloze paarden en koeien  
  te vondeling gelegd in een wereld  
  van gras  
  
  nu ik opnieuw door gods landerijen  
  moet gaan vind ik geen schrede  
  waarop ik terug kan keren, alleen  
  een kleine hand in de mijne  
  die zich krampt als de geweldige lijven  
  van het vee kreunen en snuiven  
  van vrede.  
  
  Rutger Kopland,  
  uit Onder het vee
  Amsterdam: G.A. van Oorschot
-
-