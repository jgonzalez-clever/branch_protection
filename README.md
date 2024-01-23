# BranchProtection


### Workflow automatizado para configurar proteccion de ramas

La herramienta se ejecuta mediante un archivo .json el cual guarda la configuracion de las protected branches. El archivo config.json esta cargado en el directorio root del repositorio y es usado por el workflow "SET_BRANCH_PROTECTION.yml".
Las branches que son configurables como "protegidas" son la DEFAULT BRANCH de cada repositorio y las ramas que ya estan protegidas pre-run del workflow.

### Funcionamiento

La herramienta esta compuesta por 2 steps
  -  El primer step se encarga de escribir el contenido del config.json al github_output del action, guardandolo en la variable $BRANCH_CONFIGURATION para asi poder ser usado en el segundo step
  -  El segundo step recorre X cantidad de repositorios dentro de una organizacion de github. Utilizando la REST API de github y haciendo requests a las BRANCHES, BRANCHES PROTEGIDAS y DEFAULT BRANCHES
