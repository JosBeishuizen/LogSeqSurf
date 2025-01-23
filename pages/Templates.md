- Entry
  template:: Actieregel
  template-including-parent:: false
	- ## <% time %>
- Journal
  template:: journaltemplate
  template-including-parent:: false
	- ## ⛅ , °
	- tags:: minimal-query
	  #+BEGIN_QUERY 
	  {:title "⛅ , °"
	   :query [:find (pull ?b [*])
	     :where 
	       [?b :block/page ?p]
	       [?b :block/refs ?t]
	       [?t :block/name "☀️"]
	   ]
	   :result-transform ( fn [result] [(rand-nth result)] )
	  :breadcrumb-show? true
	   :collapsed? false
	  }
	  #+END_QUERY
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
-