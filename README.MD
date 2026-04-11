# JWebMP Bill of Materials (BOM)

[![Build](https://github.com/JWebMP/BOM/actions/workflows/maven-publish.yml/badge.svg)](https://github.com/JWebMP/BOM/actions/workflows/build.yml)
[![Maven Central](https://img.shields.io/maven-central/v/com.jwebmp/jwebmp-bom)](https://central.sonatype.com/artifact/com.jwebmp/jwebmp-bom)
[![Maven Snapshot](https://img.shields.io/nexus/s/com.jwebmp/jwebmp-bom?server=https%3A%2F%2Foss.sonatype.org&label=Maven%20Snapshot)](https://oss.sonatype.org/content/repositories/snapshots/com/jwebmp/jwebmp-bom/)
[![License](https://img.shields.io/badge/License-Apache%202.0-blue)](https://www.apache.org/licenses/LICENSE-2.0)

![Java 25+](https://img.shields.io/badge/Java-25%2B-green)
![Guice 7](https://img.shields.io/badge/Guice-7%2B-green)
![Vert.X 5](https://img.shields.io/badge/Vert.x-5%2B-green)
![Maven 4](https://img.shields.io/badge/Maven-4%2B-green)

**Centralised version management** for the entire [JWebMP](https://jwebmp.com) ecosystem — import this single BOM to align all JWebMP core modules, plugins, and connectors at compatible versions without hardcoding any version strings in your project.

Built on [Maven BOM](https://maven.apache.org/guides/introduction/introduction-to-dependency-mechanism.html#bill-of-materials-bom-poms) · [JWebMP](https://jwebmp.com) · Java 25+

## 📦 Installation

### Maven

```xml
<dependencyManagement>
  <dependencies>
    <dependency>
      <groupId>com.jwebmp</groupId>
      <artifactId>jwebmp-bom</artifactId>
      <version>${jwebmp.version}</version>
      <type>pom</type>
      <scope>import</scope>
    </dependency>
  </dependencies>
</dependencyManagement>
```

Then declare dependencies without versions:

```xml
<dependency>
  <groupId>com.jwebmp.core</groupId>
  <artifactId>core</artifactId>
</dependency>
```

<details>
<summary>Gradle (Kotlin DSL)</summary>

```kotlin
dependencies {
    implementation(platform("com.jwebmp:jwebmp-bom:2.0.0-RC4"))

    implementation("com.jwebmp.core:jwebmp-core")
    // no version needed — managed by the platform
}
```
</details>

## ✨ Features

- **Single import** — one `<scope>import</scope>` declaration manages versions for all JWebMP artifacts
- **Ecosystem-wide alignment** — core, client, testlib, plugins, connectors, and build tools all move in lockstep
- **No version conflicts** — guarantees that all JWebMP modules are compiled and tested together
- **Plugin-friendly** — any JWebMP plugin (AG Grid, Web Awesome, Chart.js, FullCalendar, Angular, etc.) can be added by `groupId:artifactId` alone
- **Works with GuicedEE BOMs** — designed to be imported alongside `guicedee-bom`, `standalone-bom`, and `jakarta-bom`

## 📋 Managed Artifacts

### Core
| GroupId | ArtifactId | Description |
|---------|-----------|-------------|
| `com.jwebmp.client` | `jwebmp-client` | Client SPI — contracts, AJAX pipeline, interceptors, component model interfaces |
| `com.jwebmp.core` | `jwebmp-core` | Core component model — HTML elements, CSS builder, events, page rendering |
| `com.jwebmp.core` | `jwebmp-testlib` | Test infrastructure — base test classes, lifecycle SPIs, integration test scaffolding |

### Runtime / Connectivity
| GroupId | ArtifactId | Description |
|---------|-----------|-------------|
| `com.jwebmp` | `jwebmp-vertx` | Vert.x HTTP server connector — serves pages on the Vert.x router |
| `com.jwebmp` | `jwebmp-rabbitmq` | RabbitMQ connector |

### Angular / TypeScript
| GroupId | ArtifactId | Description |
|---------|-----------|-------------|
| `com.jwebmp.plugins` | `angular` | Angular 21 TypeScript integration |
| `com.jwebmp.plugins` | `angular-maven-plugin` | Maven plugin for Angular build pipeline |
| `com.jwebmp.plugins` | `typescript-client` | TypeScript client annotations |

### UI Components
| GroupId | ArtifactId | Description |
|---------|-----------|-------------|
| `com.jwebmp.plugins` | `web-awesome` | Web Awesome components |
| `com.jwebmp.plugins` | `web-awesome-pro` | Web Awesome Pro components |

### Data Grids
| GroupId | ArtifactId | Description |
|---------|-----------|-------------|
| `com.jwebmp.plugins` | `aggrid` | AG Grid (community) |
| `com.jwebmp.plugins` | `aggrid-enterprise` | AG Grid (enterprise) |

### Charting
| GroupId | ArtifactId | Description |
|---------|-----------|-------------|
| `com.jwebmp.plugins` | `agcharts` | AG Charts (community) |
| `com.jwebmp.plugins` | `agcharts-enterprise` | AG Charts (enterprise) |
| `com.jwebmp.plugins` | `chartjs` | Chart.js integration |

### Calendar
| GroupId | ArtifactId | Description |
|---------|-----------|-------------|
| `com.jwebmp.plugins` | `full-calendar` | FullCalendar (community) |
| `com.jwebmp.plugins` | `full-calendar-pro` | FullCalendar (pro) |

### Icon Sets
| GroupId | ArtifactId | Description |
|---------|-----------|-------------|
| `com.jwebmp.plugins` | `font-awesome` | Font Awesome 5 |
| `com.jwebmp.plugins` | `font-awesome-pro` | Font Awesome 5 Pro |

### Effects
| GroupId | ArtifactId | Description |
|---------|-----------|-------------|
| `com.jwebmp.plugins` | `easing-effects` | Easing effects |

## 🔗 Companion BOMs

For full stack projects, import these BOMs alongside the JWebMP BOM:

```xml
<dependencyManagement>
  <dependencies>
    <!-- JWebMP modules -->
    <dependency>
      <groupId>com.jwebmp</groupId>
      <artifactId>jwebmp-bom</artifactId>
      <version>${guicedee.version}</version>
      <type>pom</type>
      <scope>import</scope>
    </dependency>

    <!-- GuicedEE platform (Guice, Vert.x, Jackson, etc.) -->
    <dependency>
      <groupId>com.guicedee</groupId>
      <artifactId>standalone-bom</artifactId>
      <version>${guicedee.version}</version>
      <type>pom</type>
      <scope>import</scope>
    </dependency>

    <!-- Jakarta EE APIs -->
    <dependency>
      <groupId>com.guicedee</groupId>
      <artifactId>jakarta-bom</artifactId>
      <version>${guicedee.version}</version>
      <type>pom</type>
      <scope>import</scope>
    </dependency>
  </dependencies>
</dependencyManagement>
```

## 🤝 Contributing

Issues and pull requests are welcome — keep docs aligned with BOM changes when adding or removing managed artifacts.

## 📄 License

[Apache 2.0](https://www.apache.org/licenses/LICENSE-2.0)
