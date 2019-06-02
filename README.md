This text is in 'Start NeoLoad.txt' in this repository.

Put these files at 'C:\NeoLoadExample' to make this work without changing the path in commands.

Parts of the command:
NeoLoadCmd.exe: Opens NeoLoad
-NTS http://***.***.***.***:8080: IP Address of your NeoTys Team Server
-NTSLogin Jenkins_CI_Tester:*************************: ID and encrypted password of the NTS login you'll use for this test
-project: path of the file(s) you want to use to run for this test. For Test as Code, you'll need at least one YAML file. Test as Code before 6.10 will require an .nlp file
-launch yamlScenario: The scenario that you want to run. This can be defined in an .nlp project or in a YAML file.

Assuming that NeoLoad6.9 is installed in on a windows machine at C:\Program Files\NeoLoad 6.9

cd "C:\Program Files\NeoLoad 6.9\bin"

Example tests:

Run a test against google.com:
NeoLoadCmd.exe -NTS http://***.***.***.***:8080 -NTSLogin Jenkins_CI_Tester:************************* -leaseLicense ************************************************************:5:1 -project C:\NeoLoadExample\empty\empty.nlp C:\NeoLoadExample\search.yaml -launch yamlScenario


Run a test against google.com with separate YAML files:
NeoLoadCmd.exe -NTS http://***.***.***.***:8080 -NTSLogin Jenkins_CI_Tester:************************* -leaseLicense ************************************************************:5:1 -project C:\NeoLoadExample\empty\empty.nlp C:\NeoLoadExample\searchPopulation.yaml C:\NeoLoadExample\searchScenario.yaml C:\NeoLoadExample\searchServers.yaml C:\NeoLoadExample\searchUsersPath.yaml C:\NeoLoadExample\searchSLAs.yaml C:\NeoLoadExample\searchVariables.yaml -launch yamlScenario

Run a test against bing.com with separate YAML files:
NeoLoadCmd.exe -NTS http://***.***.***.***:8080 -NTSLogin Jenkins_CI_Tester:************************* -leaseLicense ************************************************************:5:1 -project C:\NeoLoadExample\empty\empty.nlp C:\NeoLoadExample\searchPopulation.yaml C:\NeoLoadExample\searchScenario.yaml C:\NeoLoadExample\searchServers.yaml C:\NeoLoadExample\searchUsersPath.yaml C:\NeoLoadExample\searchSLAs.yaml C:\NeoLoadExample\searchVariables01.yaml -launch yamlScenario

Run a test against neoload.com with separate YAML files:
NeoLoadCmd.exe -NTS http://***.***.***.***:8080 -NTSLogin Jenkins_CI_Tester:************************* -leaseLicense ************************************************************:5:1 -project C:\NeoLoadExample\empty\empty.nlp C:\NeoLoadExample\searchPopulation.yaml C:\NeoLoadExample\searchScenario.yaml C:\NeoLoadExample\searchServers.yaml C:\NeoLoadExample\searchUsersPath.yaml C:\NeoLoadExample\searchSLAs.yaml C:\NeoLoadExample\searchVariables01.yaml -launch yamlScenario

Run a test against multiple servers with separate YAML files:
NeoLoadCmd.exe -NTS http://***.***.***.***:8080 -NTSLogin Jenkins_CI_Tester:************************* -leaseLicense ************************************************************:5:1 -project C:\NeoLoadExample\empty\empty.nlp C:\NeoLoadExample\searchPopulation.yaml C:\NeoLoadExample\searchScenario.yaml C:\NeoLoadExample\searchServersWithFileVariable.yaml C:\NeoLoadExample\searchUsersPath.yaml C:\NeoLoadExample\searchVariables03.yaml C:\NeoLoadExample\searchSLAs.yaml -launch yamlScenario
