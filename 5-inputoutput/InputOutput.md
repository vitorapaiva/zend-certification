# Files and filesystem functions (REVISAR)

	* Two main types of functions:
		f*() functions that work with a file resource Ex: fopen()

		file*() functions that work with a filename. Ex: file_get_contents()

	* Files with resources (f*)
		* User assgined a unique identifier, the "session id"
			* Create a file resource with fopen()
				1st parameter: file name (required)
				2nd parameter: file mode (required)

			* Read with fread()
				Ex:
					$fp = fopen('file.txt', 'r');
					while(!feof($fp)){
						echo htmlspecialchars(fread(		$fp, //file
							4096 //filezise
							));
					}
					fclose($fp);

					OR

					echo htmlspecialchars(fread($fp,filesize('file.txt')));

	* Write to resources
		fwrite() and fputs() write data into a resource
			Ex:
				$fp = fopen('file.txt', 'w');
				fwrite($fp,'data...');
				fclose($fp);
	* Other functions
		fputcsv() writes and array in csv format into a file
		fprintf() writes a formatted string to a stream

	* Output files
		fpassthru() Outputs all data of a file handle directly to the output buffer. Starts at current file position. Using fread() plus escaping special character is often a better alternative

	* Directory
		chdir() changes the directory
		chroot() changes the root directory
		readdir() reads an entry from the directory handle
		rmdir() deletes a directory

	* File information
		finfo_open() create a new fileinfo resource
		finfo_file() returns information about a file

	* Filesystem
		basename() returns filename component of a path
		chmod() changes the file mode
		copy() copies a file
		file_exists() checks if a file or directory exists
		fpassthru() outputs all data of a file handle directory to the output buffer (starting at the current file position)
		fputcsv() writes daya into a resource fputs()
		rename() moves/renames a file
		unlink() deletes a file

# Streams
	* Provide a way of grouping and making available operations which have functions and actions in common

	* Parts of a data stream:
		Wrapper
		Pìpelines
		Context
		Meta Data

	* File wrappers
		* Provide information on protocols and encodings
			* Can be any file wrapper
			* Allows for two pipelines at most - for reading & writing

		* Prefix in front of a file path
			file://
			http://
			https://
			ftp://
			php://
			compress.zlib://
			compressbzip2://
			ftps://

		* Custom wrappers
			stream_wrapper_register(protocol,classname) Register a protocol; implementation is part of the class

			* The class implements standard functionality like reading, writing or changing the file position

			* php_user_filter is a predefined class in php and is used in conjunction with user-defined filters

		* Pipelines / transport

			* Code wrapper communication 
			* Contenxt: additional information for a stream (Ex: https headers for http streams)
			* Meta data: can be determined with stream_get_meta_data

		* Stream contexts

			* Set of parameters and wrappers options that can modify a stream's behavior
			* Create contexts with stream_context_create()
				* Options can be specified when the function is called
				* Parameters can be specified with stream_context_set_params()
			* Current options for a given stream can be determined by calling stream_context_get_options

		* Stream filters

			* Can be applied to stream data
				stream_filter_append($fp,'filtername')

			* Can create custom filters
				stream_filter_register(filtername,classname)

			* Class implements the following method
				function filter($in,$out,&$consumed,$closing)

# Reading and Writing
	
	* Read in the complete contents of  afile
		string file_get_contents(string filename, boolean use_include_path, resource context, int offset, int maxlen)

	* Read a file delimited by line into an array
		array file(string filename, int use_include_path)

	* Read and output a file to the output buffer
		int readfile(string filename, int use_include_path)

	* Write data into a file
		file_put_contents(string filename, mixed data, int flags, resource context)

	* Write data into a resource
		fwrite(), fputs() ...
		$fp = fopen('file.txt','w');
		fwrite($fp,'data...');
		fclose($fp);

	* Write to streams
		fprintf() printf for resources




