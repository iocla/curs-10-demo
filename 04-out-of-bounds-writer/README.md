

* recognize features of example 03
* identify values at buffer[0]..buffer[8]
* program has two stages: read indexes of buffer, overwrite indexes of buffer 
  - accepts values in decimal 
  - $ printf "%d" 0x08048661
  - watch exit code 
  - $ if ./writer; then echo "URA"; fi
  - the only way to exit with success (exit code 0) 
	is through the hidden/secret functions
* goal: exit with success
* overwrite return address 
* call hidden_function 
* call secret_function 
$ identify addresses with objdump 
	hidden_func = 0x08048661 = 134514273
	secret_func = 0x04048678 = 134514296
	
* return address at buf[6] 
  - overwrite with 134514273, harvest hurrays 
  - overwrite with 134514296, harvest hurrays, but no awsome skills? 
  - buf[6]=134514296 buf[8]=1111638594 buf[9]=1785358954
    why not buf[7] and buf[8]? 
