# ast-monorepo

Monorepo of submodules for testing purposes.

## Source Repositories

Source repositories should follow a simple naming pattern:

`ast-<LANGUAGE>-<FRAMEWORK>-<NUMERIC_INDEX>`

See Adding a New Submodule for an indepth example of this naming strategy.

### Source Repository Structure

The source code should be well-organized in each of the source repositories.

The goal is to create examples that are well organized by folder structure.

Take a basic Spring Boot Example - there are several ways to define a rest controller:

* `@RequestMapping`
* `@GetMapping` (et. al.)
* Spring `router()` DSL function

These should be well organized by the folder structure and class name:

```txt
src/main/java
    ├── com.example.ast
        ├── annotations
            ├── RequestMappingController.java
            ├── GetMappingController.java
            ├── ... other annotation controllers
        ├── dsl
            ├── WebMvcRouterController.java
            ├── WebFluxRouterController.java
```

Now just looking at the folder structure, we see the package names clearly map to the style of declaration,
and the class names map to implementation specific versions.

## Adding A New Submodule

Run the following style of command:

```bash
git submodule add <GIT_CLONE_URL> <FOLDER_TO_CLONE_INTO>
```

The naming strategy for the folder to clone into is important.

Please follow this strategy:

`<LANGUAGE>-<FRAMEWORK>-<NUMERIC_INDEX>`

For example:
  * java-spring-boot-1
  * java-spring-boot-2
  * kotlin-spring-boot-1
  * kotlin-spring-boot-2
  * scala-akka-1
  * javascript-express-1
  * typescript-express-1

etc.

## Updating Submodules

To update all submodules to the latest commit on their respective branches:

```bash
git submodule init
git submodule update --remote
```

Typically, the `main` or default branch is fine for each submodule.

Alternatively, you can run `./init.sh` to update all submodules.
