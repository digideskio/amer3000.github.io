---
layout: post
permalinks: filter-some-keys-in-multi-dimensional-arrays-in-php
title: Filter Some Keys in Multi-dimensional Arrays in PHP
---



    
    
      /**
    	* Cleans up multi-dimensional arrays.
    	* 1st dimension is a simple index
    	* 2nd dimension includes the desired keys
    	*
    	* @param mixed $array
    	* @param mixed $keysToInclude
    	*/
    	public function cleanUpArray($array, $keysToInclude){
    		$returnArray = array();
    		$i = 0;
    		foreach($array as $item){
    
    			foreach($keysToInclude as $key){
    				$returnArray[$i][$key] = $item[$key];
    			}
    			$i++;
    		}
    
    		return $returnArray;
    	}
