- ssh-keygen -t ed25519 -C "your_email@example.com"
  logseq.order-list-type:: number
- Filenaam: mykey.pub. Verplaats deze file naar ~/.ssh
  logseq.order-list-type:: number
- $ eval "$(ssh-agent -s)"
  logseq.order-list-type:: number
- ssh-add ~/.ssh/mykey
  logseq.order-list-type:: number
- Voeg nieuwe sleutel toe aan github account.
  logseq.order-list-type:: number
	- cd ~/.ssh
	  logseq.order-list-type:: number
	- cat mykey.pub
	  logseq.order-list-type:: number
	- Copierr sleutel
	  logseq.order-list-type:: number
	- Ga na github website en login met Authenticator
	  logseq.order-list-type:: number
	- Ga naar settings>SSH and GPG keys
	  logseq.order-list-type:: number
	- New SSH key
	  logseq.order-list-type:: number
	- Copieer sleutel
	  logseq.order-list-type:: number
- Check: 
  logseq.order-list-type:: number
	- ssh -T git@github.com
	  logseq.order-list-type:: number
	- ssh-add -l -E sha256
	  logseq.order-list-type:: number
- Git opzetten
  logseq.order-list-type:: number
	- git config --global user.name "JosBeishuizen"
	  logseq.order-list-type:: number
	- git config --global user.email "josbeishuizen@gmail.com"
	  logseq.order-list-type:: number
	- Add a file named config (without any extension) under ~/.ssh
	  logseq.order-list-type:: number
	  Edit it using your preferred text editor, add following text into the file
	  # github
	  Host github.com
	      User git
	      HostName github.com
	      PreferredAuthentications publickey
	      IdentityFile <path to your private key file>
	      ServerAliveInterval 300
	      ServerAliveCountMax 10
	  Test if it worked using command
		- ssh -T github.com
		  logseq.order-list-type:: number
- Repo clonen
  logseq.order-list-type:: number
	- cd ~/Documents
	  logseq.order-list-type:: number
	- git clone git@github.com:JosBeishuizen/LogSeqSurf.git
	  logseq.order-list-type:: number
- Repo openen met LogSeq en klaar!
  logseq.order-list-type:: number