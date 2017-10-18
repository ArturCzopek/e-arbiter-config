## e-Arbiter - configuration

#### What it is?
It's a repository with yml config files for each Spring microservices.

#### Why it is used?
Because holding configuration in each module separately is confusing and harder to maintain.
With this approach we have everything in one place.

Also, Spring Cloud server allows us to change properties in runtime. What does it mean? For example, if we have remote repo for prod app, we can update some values and after that, Spring will update his values, without recompiling! Great, heh?

#### How to use it?
Currently, application cannot run without this repo. Prod version probably will use remote repo.
For development user can sometimes change something locally.

Instruction:

-Download this repository.

-From file `env.env` copy enviroments and add to your environment. (If you have problem on Windows, write message to Artur)

-Change `E_ARB_ROOT_FOLDER` env variable value. It should point to your main folder with three projects: e-arbiter, e-arbiter-utils, e-arbiter-config.

If you change something, COMMIT IT, BUT WITHOUT PUSH! Otherwise, yours changes won't be visible for Spring.

If you change something there and you want to add this to master version, create another branch, new pull request, and attach it to proper Trello's ticket. Sometimes changes will be needed!

#### Possibly problems
Sometimes IJ cannot see your env variables. Remember about adding it to your env and to IJ!! Otherwise, IJ can throw some errors and you will be forced to use console (it isn't wrong but debugging is harder...). Suggested plugin: `envFile`

## ELK stack - configuration

#### Download ELK
Download and extract [elasticsearch], [kibana], [logstash].

#### Setup ELK
In file `env.env` change the environments `E_ARB_{option}_RUN` where options is type of tool
(ES - elasticsearch, KIB - kibana, LOG - logstash) to a directories u have just extract tools.

#### Results
The log charts can be seen via [results].
I recommend to setup kibana with columns `Time, level, class, longmessage` for better visibility.
You can add columns from left side panel with label available fields.
The columns can be removed by clicking crossroad icon near column names under the main chart.

[elasticsearch]: <https://www.elastic.co/downloads/elasticsearch>
[kibana]: <https://www.elastic.co/downloads/kibana>
[logstash]: <https://www.elastic.co/downloads/logstash>
[results]: <http://localhost:5601>
