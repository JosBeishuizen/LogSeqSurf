- Journal
  template:: journaltemplate
  template-including-parent:: false
	- ## ⛅ , °
	- collapsed:: true
	  #+BEGIN_QUERY 
	  {:title [:b.header "Om de dag te beginnen"]
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
	-
- #Gezien
  template:: Cultuur
  template-including-parent:: false
	- Titel::
	  Tags:: 
	  Gezien-op:: 
	  Opm::
	  Cijfer::
- #Abo
  template:: Abo
  template-including-parent:: false
	- naam:: 
	  type:: 
	  prijs::
	  per-maand:: 
	  per-jaar::
- #Quote
  template:: Quote
  template-including-parent:: false
	- #+BEGIN_QUERY
	  {:title "Citaat"
	  :query [:find (pull ?b [*])
	       :where
	       [?b :block/page ?p]
	       [?b :block/refs ?t]
	       [?t :block/name "☀️"]
	  ]
	  :result-transform (fn [result] [(rand-nth result)] )
	  }
	  #+END_QUERY
	- - # # Daily note
	    template:: daily
	    template-including-parent:: false
	  	- up:: placeholder
	  	- **A quote to think about**:
	  		- {{renderer :interstitial, random, "quote" }}
	  	- **Note self**:
	  		- {{renderer :interstitial, yesterday, "NTNDS" }}
	  	- ## End of day checklist 📝
	  		- TODO Write ntnds here:
	  			- Don't forget to write some encouraging words to your tomorrows self [[ntnds]]
	  		- TODO Today I learned
	  	- ## Planning
	  		- TODO vitamins
	  		- {{renderer :unfinishedBusiness}}
	  		- TODO What is todays _frog_?
	  	- ## Journal
	  		- **9:00** [[BHighlights]]