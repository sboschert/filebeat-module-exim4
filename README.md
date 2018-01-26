# filebeat-module-exim4

This is a simple
[Filebeat](https://www.elastic.co/de/products/beats/filebeat|Filebeat) module
that parses main logs and reject logs created by
[Exim 4](https://www.exim.org).


## Installation

These instructions assume you have a working Filebeat installation.

 1. Set up Exim to log its time zone:

    Filebeat needs to know what time zone your logs are in. Therefore, please
    add the following configuration directive to your Exim configuration:

    ```
    log_timezone = true
    ```

    Otherwise, this Filebeat module will assume your logs are in UTC.

 2. Install module files:

     1. Copy `module/exim4` to your module directory
        (usually `/usr/share/filebeat/module/`):
   
        ```
        cp -R module/exim4 /usr/share/filebeat/module/
        ```
   
     2. Copy the module descriptor to your modules.d directory
        (usually `/etc/filebeat/modules.d`):
   
        ```
        cp modules.d/exim4.yml.disabled /etc/filebeat/modules.d/
        ```

 3. Test whether or not the module was picked up by Filebeat:
 
    ```
    filebeat modules list | grep exim4
      => exim4
    ```
    
 4. Enable the module:
 
    ```
    filebeat modules enable exim4
    ```
    
 5. Restart Filebeat (if necessary).
 
 
## Contributing
 
If you'd like to contribute to this project, please feel free to contact any
of the
[contributors](https://github.com/sboschert/filebeat-module-exim4/graphs/contributors)
or simply create a new pull request with your suggested changes.


## Copyright & License

Copyright &copy; 2018 Sebastian Boschert

```
Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

   http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
```