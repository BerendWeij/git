## Git Workflow

### Werkwijze met branches: feature branch strategy
Binnen onze Game Studio hanteren wij een feature branch strategy voor ons versiebeheer. Dit houdt in dat we werken met de volgende branches:
* master branch
* develop branch. (hier zit altijd de laatste, gemergde versie van ons project in)
* feature branches

![](https://raw.githubusercontent.com/wiki/BAStudio/OperationStarfall/images/gitflow.png?token=ABJU6LSLUS7OVRFA7QSZO73A6WBBK)

##### Feature branches
Over het algemeen werk je binnen een feature branch aan een nieuwe feature. Deze branches hebben de volgende naamgeving: 

`feature/nieuwe-feature-naam`

Een voorbeeld hiervan is: `feature/jump-mechanic`

**Let op:** schrijf alles met kleine letters

Een feature staat gelijk aan een user story. 
Zodra een feature af is dan wordt er een pull request aangemaakt. Deze pull request wordt aangemaakt ten opzichte van de develop branch. We willen de feature branch 'mergen' in de develop branch.

Good practises:
* Feature branches 'leven' maar heel kort. Hoe langer ze bestaan, des te meer kans er is op merge problemen. Ook is het reviewen van een pull request veel meer werk als een feature branch heel lang bestaat.
    * Feature branches worden verwijderd nadat ze gemerged zijn
* Merge een feature branch niet naar een andere feature branch. Dit is een indicatie dat de feature branch al te lang bestaat. Dit vraagt om merge problemen.

## PULL REQUEST POLICIES

Onze develop branch is de default branch van onze repository. Dit is omdat we standaard alleen maar ons werk naar develop mergen. De master branch daar staat al het gemergde werk na een sprint.

De develop branch moet ALTIJD te compilen zijn. Om die reden mergen we via pull requests.
De develop branch is 'protected' en er mag dan ook niet direct naar gemerged worden. Ook moeten de pull request op zijn minst door de code owner bekeken worden.

Bij het doornemen van een pull request wordt er gekeken of:
* de code de code conventions goed heeft doorgevoerd
* de feature voldoet aan onze DoD

Als dit niet het geval is dan volgt er feedback en wordt de pull request niet doorgevoerd.

### Comitten

In een werkdag proberen we meerdere keren te comitten. Comitten zorgt ervoor dat we makkelijker kunnen mergen en dat we bij eventuele merge errors makkelijker handmatig kunnen mergen.
Aangezien we met feature branches werken kun je vaak ook direct pushen naar de feature branch. let er wel op dat je de build in de branch niet stuk maakt voor collega's waar je mee samenwerkt.

    # Commit template:
    Je commit message is altijd een antwoord op de vraag "wat voegt deze commit toe"
    Een commit message kan dan bijvoorbeeld zijn "adds the jump mechanic" of "fixes the bug with the restart button"

#### Einde van een sprint
Het werk van een sprint mag aan het einde van een sprint naar de master branch. De volgorde hiervan is als volgt:
* Alle (afgeronde) feature branches worden gemerged met de ​develop branch ​(in de meeste gevallen is dit al gebeurd tijdens de sprint). Met afgerond wordt bedoeld: de feature voldoet aan onze DoD. ​Het mergen van branches gebeurd door middel van pull requests.
* Zodra de feature branches zijn gemerged met develop, dan wordt hij gemerged met de ​master branch. Dit mag alleen door de code owner gedaan worden.
De master branch wordt vervolgens getagged met het sprint nummer gevolgd door de epic code gevolgd door de epic sprint code:
`git tag -a 15.3.2`

