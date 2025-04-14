# 🧩 Atelier 1 - Injection de dépendances en Java - Omar Elkrimi

Ce projet illustre les différents types d’injection de dépendances en Java, notamment avec le Framework **Spring** (XML & Annotations).

## 🎯 Objectifs

- Appliquer le principe d’inversion de contrôle (IoC)
- Mettre en place une architecture découplée via interfaces `IDao` et `IMetier`
- Implémenter l’injection :
  - Statique
  - Dynamique (avec `Class.forName`)
  - Spring XML
  - Spring Annotation

## 🧱 Structure du projet

- `dao.IDao` : Interface de récupération de données
- `dao.DaoImpl` : Implémentation concrète
- `metier.IMetier` : Interface métier
- `metier.MetierImpl` : Contient une dépendance vers `IDao`
- `pres.*` : 5 classes de présentation (MainStatic, MainDynamic, MainSpringXML, MainSpringAnnotation, etc.)

## 💡 Méthodes d'injection

- 🔵 **Statique** : via `new`
- 🟢 **Dynamique** : via `Reflection API`
- 🟠 **Spring (XML)** : configuration via `applicationContext.xml`
- 🔴 **Spring (Annotation)** : configuration avec `@Component`, `@Autowired`, etc.

## 🚀 Exécution

Lancer les classes de présentation (`Main*`) depuis IntelliJ pour tester chaque méthode d’injection.

## 📁 Exemple de config Spring XML

```xml
<beans xmlns="http://www.springframework.org/schema/beans"
       ...>
  <bean id="dao" class="dao.DaoImpl"/>
  <bean id="metier" class="metier.MetierImpl">
    <property name="dao" ref="dao"/>
  </bean>
</beans>
