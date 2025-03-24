# LatteSite Structured Data Generator

This is an SEO Structured Data generator written in Java.

This is primary a module for the main LatteSite Static Site Generator project, but it may be used as a stand-alone generator.

For more information, please visit the main LatteSite SSG repository.

## Releases

Releases can be found in the [/releases/](https://github.com/lattesite/lattesite-structured-data/tree/master/releases) folder.



## Discord

- https://discord.gg/tmcydvJdrq



## Quick Example

```java
package lattesite.structured.data.examples;

import lattesite.structured.data.enumeration.GenderType;
import lattesite.structured.data.schemas.StructuredDataPerson;
import lattesite.structured.data.services.StructuredDataService;

public class MainExample {

    public static void main(String[] args) throws Exception {

        // Initiate the service
        StructuredDataService structuredDataService = new StructuredDataService();

        // Create a new Person Structured Data
        String name = "Steve";
        String description = "Homer Jay Simpson is the main protagonist of the American animated television series The Simpsons and patriarch of the titular Simpson family.";
        String image = "https://upload.wikimedia.org/wikipedia/en/0/02/Homer_Simpson_2006.png";
        GenderType gender = GenderType.MALE;
        String url = "https://en.wikipedia.org/wiki/Homer_Simpson";
        String jobTitle = "Safety inspector at Springfield Nuclear Power Plant";
        String knowsAbout = "Donuts";
        String[] sameAs = new String[]{"https://x.com/homerjsimpson"};
        String givenName = "Homer Jay";
        String familyName = "Simpson";

        StructuredDataPerson person = new StructuredDataPerson(
                name,
                description,
                image,
                gender,
                url,
                jobTitle,
                knowsAbout,
                sameAs,
                givenName,
                familyName
        );

        // Generate JSON
        String json = structuredDataService.toJSON(person);

        System.out.println(json);

        /*

            {
                "@context": "https://schema.org/",
                "@type": "Person",
                "url": "https://en.wikipedia.org/wiki/Homer_Simpson",
                "image": "https://upload.wikimedia.org/wikipedia/en/0/02/Homer_Simpson_2006.png",
                "description": "Homer Jay Simpson is the main protagonist of the American animated television series The Simpsons and patriarch of the titular Simpson family.",
                "sameAs": [
                    "https://x.com/homerjsimpson"
                ],
                "knowsAbout": "Donuts",
                "jobTitle": "Safety inspector at Springfield Nuclear Power Plant",
                "gender": "https://schema.org/Male",
                "givenName": "Homer Jay",
                "familyName": "Simpson",
                "name": "Steve"
            }

         */

    }

}
```

## License

TBA