# 📦 JWebMP Bill of Materials (BOM)

[![JDK](https://img.shields.io/badge/JDK-25%2B-0A7?logo=java)](https://openjdk.org/projects/jdk/25/)
[![Build](https://img.shields.io/badge/Build-Maven-C71A36?logo=apachemaven)](https://maven.apache.org/)
[![License](https://img.shields.io/badge/License-Apache_2.0-blue.svg)](https://www.apache.org/licenses/LICENSE-2.0)

Centralizes compatible dependency versions for all JWebMP modules and plugins.
Import this BOM to avoid hardcoding versions for JWebMP artifacts.

## 🔧 Usage (Maven)
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
  <artifactId>jwebmp-core</artifactId>
</dependency>
```

## 📋 Managed Artifacts

### Core
| GroupId | ArtifactId | Description |
|---------|-----------|-------------|
| `com.jwebmp.client` | `jwebmp-client` | Client library for JWebMP |
| `com.jwebmp.core` | `jwebmp-core` | Core component model |
| `com.jwebmp.core` | `jwebmp-testlib` | Testing utilities |

### Runtime / Connectivity
| GroupId | ArtifactId | Description |
|---------|-----------|-------------|
| `com.jwebmp` | `jwebmp-vertx` | Vert.x connector |
| `com.jwebmp` | `jwebmp-rabbitmq` | RabbitMQ connector |

### Angular / TypeScript
| GroupId | ArtifactId | Description |
|---------|-----------|-------------|
| `com.jwebmp.plugins` | `angular` | Angular 20 TypeScript integration |
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

## 📝 License & Contributions
- License: Apache 2.0
- Issues/PRs welcome; keep docs aligned with BOM changes.
