# lib_mysqludf_json

### Instructions
I forked this repo from [mysqludf/lib_mysqludf_json](https://github.com/mysqludf/lib_mysqludf_json) and made some modifications 👇

I renamed functions `json_array` & `json_object` as `udf_json_array` & `udf_json_object`, because `json_array` & `json_object` have became mysql native functions since version 5.7.8. So if you don't change their name, you can't create udf with the same name as native functions'.

And of course, I changed `json_array` & `json_object` udf' names in `lib_mysqludf_json.sql`.

### Original readme file
Original readme file is [here](https://github.com/mysqludf/lib_mysqludf_json/blob/master/README.md)

### Compile lib_mysqludf_json.so
I deleted the old  lib_mysqludf_json.so file, not only because it has udf with name like `json_array`/`json_object`, but also because it's just a 32-bit version.

So, you can compile it yourself using command `gcc $(/your/mysql/bin/path/mysql_config --cflags) -shared -fPIC -o lib_mysqludf_json.so lib_mysqludf_json.c`.