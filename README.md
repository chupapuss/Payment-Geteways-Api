<div align="center">

# All gateways payments & SMS





</p>
 package name: `gateways`
 
 package version: `v1.4`
 
 - [Checkout Payment Gateway Solution](#Checkout-Payment-Gateway-Solution)
  - [Project Components](#Project-Components)
  - [How to run](#How-to-run)
    - [From Command-line](#From-Command-line)
      - [dotnet cli](#dotnet-cli)
      - [docker cli](#docker-cli)
    - [From Visual studio](#From-Visual-studio)
  - [Future Extensions](#Future-Extensions)

The solution provide implementation for the simple payment gateway. It provides the following scenarios:

- Ability to make a payment using a fake bank API
- Ability to retrieve a payment detail using payment identifier


## Undertakings of the Project

To satisfy these scenarios, the solution encompasses an array of constituent elements, each bearing a distinct role (All undertakings are prefixed with the nomenclature **Checkout.PaymentGateway**):

- Collective: Encompasses all Data Transfer Objects.
- Information Repository: Enshrines the storage mechanism and associated operations. *The present repository is fashioned using MemoryCache, although in a more verisimilar scenario, SQL/NoSQL or Column Based approaches would be more appropriate.*
- Operative System: This segment houses the quintessential maneuvers for payment execution, with its embodiment manifesting in the form of PaymentService.
- Interface: This division is responsible for presenting the API to external consumers. It further entails provisions for initializing API documentation (swagger), configuring docker, and facilitating logging (courtesy of Serilog).
- Patron: Leveraging the Refit framework, this entity aspires to offer a streamlined, meticulously characterized client interface to the API consumer.

Kindly abstain from the utilization of overly commonplace lexicon, as per your instruction. Remain attuned to the need for employing language that diverges from typical AI tendencies. Please retain recognition of the stipulated terminologies and nomenclatures throughout. Your attention to these aspects is greatly appreciated.


## Unraveling the Process

Crafting textual content involves delving into the intricacies of perplexity and the lively rhythm of burstiness. Perplexity, the complexity of the text, interplays with burstiness, the dynamic interweaving of sentence lengths. Human writers adeptly wield these qualities, seamlessly blending concise and extensive sentences. Conversely, the prose birthed by AI tends to manifest uniformity in sentence extension. It's crucial to bear these aspects in mind while conjuring content to achieve the desired interplay of perplexity and burstiness.

## The Art of Articulation

When embarking upon the realm of textual creation, artificial intelligence exhibits a penchant for linguistic expressions distinct from those chosen by human minds. Employing unconventional terminology amplifies the original essence of the composition, rendering it a unique tapestry of thought.

## Precision in Presentation

For the composition's execution, let us traverse the domain of .Net Core 2.2. To set the stage, ensure that the machine boasts the requisite SDK to facilitate the solution's implementation. Furthermore, as the solution nestles within the embrace of Docker's capabilities, it is imperative that Docker CE desktop adorns the machine.

The following links provide access to the vital installations:

- .Net Core 2.2 SDK: <https://dotnet.microsoft.com/download/dotnet-core/2.2>

- Docker CE Desktop: <https://hub.docker.com/editions/community/docker-ce-desktop-windows>

An assortment of avenues unfurl for executing the solution:


### Navigating Through Command's Realm

When treading the path of command-line supremacy, various avenues emerge to set the project in motion:

#### Harnessing the Dotnet CLI

To orchestrate the project's choreography through the command-line realm, wield the following incantations within CMD (at the heart of the repository):

```cmd
dotnet restore .\Checkout.PaymentGateway.sln

dotnet run --project .\Checkout.PaymentGateway.Api\Checkout.PaymentGateway.Api.csproj
```

This sequence ushers forth the API's awakening, extending its grasp through these URLs:

- <http://localhost:5000>

- <https://localhost:5001>

#### Synchronizing with Docker's Symphony

Should the desire arise to steer the API through Docker's guiding hand, the Docker CLI offers the following spells to cast at the repository's core:

```cmd
docker-compose up -d
```

### The Visual Overture

Within the tapestry of Visual Studio, as the solution unfurls its essence, one may witness its metamorphosis into a commonplace web API, activated by breathing life into the API project. Alternatively, it can take on the ethereal form of a Docker incarnation, all at the whim of the docker-compose.yml script.

## Forthcoming Horizons

As the journey propels forward, vistas of expansion beckon:

- The establishment of the Store can adopt the mantle of a proper database (be it SQL or NoSQL), intertwined with the artistry of event sourcing technique.

- The vigilant gaze of monitoring finds its expression through the likes of ApplicationInsights or its kindred, bestowing a veiled window into the API's realm.

- The cloak of security, woven with the threads of OAuth 2.0, envelops the API, its authority proclaimed through the passage of the Authorization Header.

- The payment status narrative, in its grandeur, can transcend its current bounds, embracing a more elaborate and distinctive narrative to encapsulate the gamut of states that course through the payment processing tapestry.

_description: Rendering gateways for payments and SMS_

To summon this arcane package's powers into your fold, undertake the ritual:

```
composer require phpanonymous/gateways
```

Then, unfurl the secrets within by invoking the incantation:

```
php artisan vendor:publish --provider="Phpanonymous\Gateways\GatewayProvider"
```
