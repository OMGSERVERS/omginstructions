# How to Create a New Defold Project Using a Project Template

Follow the instructions in the [Defold Editor Templates](https://defold.com/manuals/editor-templates/) guide.

## OMGSERVERS `welcome.edn` File

```edn
{:new-project
  {:categories [
    {:label "OMGSERVERS"
     :templates [
       {:name "Template Project"
        :description "OMGSERVERS template project with integrated SDKs and sample code."
        :image "empty.svg"
        :zip-url "https://github.com/OMGSERVERS/omgdefold/archive/refs/heads/main.zip"
        :skip-root? true}]
    }]
  }
}
