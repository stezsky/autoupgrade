# Auto upgrade tool

The repository contains an example of using automation for upgrading source code as part of the [EventStorming, DDD a mikroslužby: jak zvládat komplexní systémy](https://www.datascript.cz/it-konference/eventstorming-ddd-a-mikrosluzby-jak-zvladat-komplexni-systemy/) conference.

## Open Rewrite

OpenRewrite is an open-source automated refactoring ecosystem for source code, enabling developers to effectively eliminate technical debt within their repositories.
It consists of an auto-refactoring engine that runs prepackaged, open-source refactoring recipes for common framework migrations, security fixes, and stylistic consistency tasks – reducing your coding effort from hours or days to minutes. Build tool plugins like the OpenRewrite Gradle plugin and the OpenRewrite Maven plugin help you run these recipes on one repository at a time.
While the original focus was on the Java language, the OpenRewrite community is continuously expanding language and framework coverage. Thousands of great individuals and teams are working together to make software seamless to update and continuously secure.

See detail on [Open rewrite page](https://docs.openrewrite.org/)

### How to run open rewrite recipes

1. Build and install recipe artefact (`./mvnw install`)
1. Check out the maven project where recipe artefact should be applied
1. Apply recipe 
    ````shell
    mvn org.openrewrite.maven:rewrite-maven-plugin:6.3.1:run \
      -Drewrite.recipeArtifactCoordinates=cz.stezsky.autoupgrade:autoupgrade:0.0.1-SNAPSHOT \
      -Drewrite.activeRecipes=cz.stezsky.autoupgrade.recipes.ServiceUpgrade # Recipe to run
    ````
