# Writing hashes in Ruby
Today I learned that there are multiple ways to write hashes that map to symbols in Ruby.

**String to symbol:**

	h = { "elem": "elem" }	
	  => {:elem=>"elem"}

This method converts the string into a symbol. Not reccommended, because this might be confusing. At first glance you might think it is mapping to a string, which is perfectly valid, but the behavior is different, and it converts the string into a symbol.

**Symbol key:**

	h = { :name => "Julio" }
	  => {:name=>"Julio"}
	  
This method uses plain symbols.
