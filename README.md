# 🛒 E-commerce Microservices Backend

Un backend de e-commerce implementado con Spring Boot y Spring Cloud utilizando arquitectura de microservicios empresarial.

## 📝 Descripción

Este proyecto es un **POM padre** que gestiona las dependencias y configuraciones comunes para un sistema de e-commerce basado en microservicios. Proporciona la estructura base y las configuraciones necesarias para desarrollar microservicios escalables, observables y mantenibles con capacidades de monitoreo, trazabilidad distribuida y documentación automática.

## 🧰 Tecnologías Utilizadas

### Core Framework

- ☕ **Java 11**
- 🌱 **Spring Boot 2.5.7**
- ☁️ **Spring Cloud 2020.0.4**
- 🧪 **Maven** (Gestión de dependencias)

### Desarrollo y Productividad

- ✨ **Lombok 1.18.38** (Reducción de código boilerplate)
- 📚 **SpringDoc OpenAPI 1.6.3** (Documentación automática de APIs)
- ⚙️ **Spring Boot Configuration Processor** (Autocompletado de propiedades)

### Microservicios y Resilencia

- 🔄 **Resilience4j** (Circuit Breaker, Rate Limiting, Bulkhead)
- 🌐 **Spring Cloud Gateway** (API Gateway)
- 🔍 **Spring Cloud Service Discovery** (Eureka)

### Observabilidad y Monitoreo

- 📊 **Micrometer + Prometheus** (Métricas)
- 🔍 **Spring Cloud Sleuth + Zipkin** (Trazabilidad distribuida)
- 📈 **Spring Boot Actuator** (Health checks y endpoints de gestión)

### Testing y Calidad

- 🧪 **JUnit 5** (Testing framework)
- 📊 **JaCoCo 0.8.7** (Cobertura de código)
- 🔧 **Maven Surefire 3.0.0-M7** (Ejecución de pruebas)

### Utilidades

- 📅 **Jackson JSR310** (Serialización de fechas Java 8+)

## 🌟 Características

### Arquitectura

- 🧩 Arquitectura de microservicios empresarial
- ⚙️ Configuración centralizada de dependencias
- 🔄 Patrones de resilencia (Circuit Breaker, Retry, Bulkhead)
- 🌐 API Gateway para enrutamiento centralizado

### Observabilidad

- 📊 Métricas con Prometheus y Micrometer
- 🔍 Trazabilidad distribuida con Sleuth y Zipkin
- 📈 Health checks y monitoreo con Actuator
- 📚 Documentación automática de APIs con OpenAPI

### Calidad y Testing

- ✅ Pruebas automatizadas con JUnit 5
- 📈 Análisis de cobertura de código con JaCoCo
- 🔧 Configuración optimizada de Maven

### DevOps

- 📦 Gestión de distribución de artefactos en GitHub Packages
- 🏗️ Configuración de build reproducible
- 🔄 Integración continua preparada

## ✅ Requisitos Previos

- ☕ **Java 11** o superior
- 🔧 **Maven 3.6+**
- 🖥️ **IDE** compatible con Java (IntelliJ IDEA, Eclipse, VS Code)
- 📊 **Prometheus** y **Zipkin** (opcional, para observabilidad completa)

## 🚀 Instalación y Uso

### 1. Clonar el Repositorio

```bash
git clone https://github.com/EcommerceCoZam/ecommerce-parent
cd ecommerce-parent
```

### 2. Compilar el Proyecto

```bash
# Compilación básica
mvn clean compile

# Compilación con pruebas
mvn clean test

# Generar reporte de cobertura
mvn clean test jacoco:report
```

### 3. Usar como POM Padre

En tus microservicios, agrega este POM como padre:

```xml
<parent>
    <groupId>com.selimhorri</groupId>
    <artifactId>ecommerce-microservice-backend</artifactId>
    <version>0.1.0</version>
</parent>
```

### 4. Desplegar Artefactos

```bash
# Desplegar a GitHub Packages
mvn clean deploy

# Solo instalar localmente
mvn clean install
```

## 🗂️ Estructura del Proyecto

```
ecommerce-microservice-backend/
├── pom.xml                 # POM padre con dependencias centralizadas
├── README.md              # Documentación del proyecto
└── .github/
    └── workflows/         # Pipelines de CI/CD (si aplicable)
```

### Dependencias Incluidas

#### 🌱 Spring Boot Core

- `spring-boot-starter` - Starter básico
- `spring-boot-starter-actuator` - Monitoreo y health checks
- `spring-boot-configuration-processor` - Procesamiento de configuración

#### ☁️ Spring Cloud

- `spring-cloud-starter-circuitbreaker-resilience4j` - Resilencia
- `spring-cloud-starter-sleuth` - Trazabilidad distribuida
- `spring-cloud-sleuth-zipkin` - Exportación a Zipkin

#### 📊 Observabilidad

- `micrometer-registry-prometheus` - Métricas para Prometheus
- `springdoc-openapi-ui` - Documentación automática de APIs

#### 🧪 Testing

- `spring-boot-starter-test` - Testing framework completo

## ⚙️ Configuración

### Propiedades Principales

| Propiedad                | Valor    | Descripción                  |
| ------------------------ | -------- | ---------------------------- |
| `java.version`           | 11       | Versión de Java              |
| `spring-cloud.version`   | 2020.0.4 | Versión de Spring Cloud      |
| `lombok.version`         | 1.18.38  | Versión de Lombok            |
| `springdoc.version`      | 1.6.3    | Versión de SpringDoc OpenAPI |

### Plugins Configurados

- **Maven Compiler**: Configurado para Java 11 con soporte para Lombok
- **Maven Surefire**: Ejecución optimizada de pruebas unitarias
- **JaCoCo**: Generación automática de reportes de cobertura
- **Spring Boot**: Empaquetado de aplicaciones Spring Boot

## 📊 Métricas y Monitoreo

Este POM incluye dependencias para:

- **Actuator endpoints**: `/actuator/health`, `/actuator/metrics`, `/actuator/info`
- **Prometheus metrics**: Exportación automática de métricas
- **Zipkin tracing**: Trazabilidad distribuida de requests
- **OpenAPI documentation**: Documentación automática en `/swagger-ui.html`

## 🧪 Testing

### Ejecutar Pruebas

```bash
# Pruebas unitarias
mvn test

# Pruebas con reporte de cobertura
mvn test jacoco:report

# Pruebas con perfil específico
mvn test -Dspring.profiles.active=test
```

### Estructura de Testing

- **JUnit 5**: Framework principal de testing
- **Spring Boot Test**: Autoconfiguración para testing de Spring Boot
- **Mockito**: Mocking framework (incluido en spring-boot-starter-test)

## 📚 Documentación Adicional

- [Spring Boot Documentation](https://docs.spring.io/spring-boot/docs/2.5.7/reference/htmlsingle/)
- [Spring Cloud Documentation](https://docs.spring.io/spring-cloud/docs/2020.0.4/reference/html/)
- [JaCoCo Documentation](https://www.jacoco.org/jacoco/trunk/doc/)

## 🤝 Contribución

1. 🔀 Haz fork del proyecto
2. 🛠️ Crea una rama para tu feature:

   ```bash
   git checkout -b feature/amazing_feature
   ```

3. 💾 Commit de tus cambios siguiendo [Conventional Commits](https://www.conventionalcommits.org/):

   ```bash
   git commit -m 'feat: add some amazing_feature'
   git commit -m 'fix: resolve dependency conflict'
   git commit -m 'docs: update README with new features'
   ```

4. 🚀 Push a la rama:

   ```bash
   git push origin feature/amazing_feature
   ```

5. 🤝 Abre un Pull Request

## 📬 Contacto

Para preguntas o soporte, contacta al equipo de desarrollo.
