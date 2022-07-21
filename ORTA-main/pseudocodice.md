#### PSEUDOCODE

###### 1. USANDO UN FOR-CYCLE SU TUTTI I NODI

```python
inizializzazione
tot_morti=0 #counter per le morti
for t in range(100000): #molto alto per evitare che "tagli" la simulazione
 	#counters per ogni iterazione
 	numero_contagi=0
 	numero_malati=0
    
	for n in graph.nodes_list:
        
		if n guarito or sano or morto:
        		pass
        
    		elif n contagiato: 
			for v in vicini:
				if v sano and rnd<pi:
					v in lista contagiati
			
		    	if 1-exp(lamb*t)<=h: #n si ammala
				n malato
				numero_malati+=1
			elif t-ti>T:	#passato T, n guarisce
				n guarito
			elif rnd<qi: #se non è ancora passato T, n potrebbe morire
				n morto
				tot_morti+=1
		    	else: #nessuna delle precedenti=>n rimane contagiato
				numero_contagi+=1

        	else: #=> n malato   
            		if t-ti>T+penalità:
				m guarito
			elif rnd<qi:
				m morto
                		tot_morti+=1
           		 else: #nessuna delle precedenti=>n rimane malato
               		 	numero_malati+=1
                
 	if numero_malati==0 and numero_contagi==0:
        	break
```



###### 2. USANDO DUE LISTE (CONTAGIATI E MALATI)

```python
inizializzazione
tot_morti=0 #counter per le morti
for t in range(100000): #molto alto per evitare che "tagli" la simulazione
    
	for c in contagiati:
		for v in vicini:
			if v non contagiato and rnd<pi:
				v in lista contagiati
		
        	if 1-exp(lamb*t)<=h: #n si ammala
           		c malato
           		c in lista malati
		elif t-ti>T:	#passato T, n guarisce
			c guarito
           		c fuori da lista contagiati
		elif rnd<qi:	#se non è ancora passato T, n potrebbe morire
			c morto
            		c fuori da lista contagiati
           		 tot_morti+=1

            
	for m in malati:
		if t-ti<T+penalità:
			m guarito
            		m fuori da lista malati
		elif rnd<qi:
			m morto
           		m fuori da lista malati
            		tot_morti+=1
            
 	if malati==[] and contagiati==[]:
        break
```



