---
layout: default
#layout: minimal
title: Entschiedungsmatrix
nav_order: 4
---

## Vergleich der verschiedenen Automatisierungstools [^1] [^6]

![Kriterien festlegen:](../img/kriterien_small2.png "Title")

### <img src="../img/ansible_logo.png" width="64"> Ansible [^2] [^3]

**Architektur:** Agentenlos, basiert auf SSH und erfordert keine permanente Installation auf den Zielsystemen.

### <img src="../img/puppet_logo.png" width="64"> Puppet: [^4]

**Architektur:** Agentenbasiert, erfordert die Installation des Puppet-Agenten auf Zielsystemen.

**Einrichtung:** Puppet ist vergleichsweise einfach zu erlernen, da es eine deklarative Sprache namens Puppet DSL verwendet, die leicht zu lesen und zu schreiben ist.

**Sprache:** Puppet DSL (Domain-Specific Language), modulare und erweiterbare Syntax.

**Community und Support:** Aktive Community, ausführliche Dokumentation, kostenpflichtiger Enterprise-Support durch Puppet Enterprise.

**Skalierbarkeit:** Gut für komplexe, verteilte Umgebungen, Skalierung durch verteilte Puppet-Server und Lastenausgleich.


### Entscheidung und Schlussfolgerungen

<img src="../img/ansible_logo.png" width="64"> Ansible [^1] Die Wahl des richtigen Automatisierungstools hängt von den spezifischen Anforderungen, der vorhandenen Infrastruktur und den Präferenzen des Teams ab. Ich habe aus den unten aufgeführten Gründen Ansible gewählt:

Ansible ist bekannt für seine Einfachheit und Geschwindigkeit und ist stärker auf Orchestrierung ausgerichtet, Puppet für seine Deklarativität sowie Verwaltung komplexer Konfigurationen und Chef für seine Flexibilität und stärke für grössere Bereitstellung.

**Agentenlos und Plattformunabhängig:**

Ansible ist agentenlos und nutzt SSH oder WinRM, um mit Zielsystemen zu kommunizieren. Dies eliminiert die Notwendigkeit, Agenten auf den Zielsystemen zu installieren, was Implementierung und Wartung vereinfacht und eine Voraussetzung für den einsatz in unserer Umgebung ist.

**Umfangreiche Community und Unterstützung:**

Ansible verfügt über eine große und aktive Community, die eine Vielzahl von Dokumentationen, Tutorials und Plugins bereitstellt. Bei Fragen oder Problemen stehen Foren und die Community zur Unterstützung zur Verfügung[^5]

**Zukünftige Erweiterbarkeit:**

Mit Ansible können wir nicht nur Windows-Updates automatisieren, auch andere Hersteller die wir im Netzwerkbereich einsetzen, stellen Ansible-Module zur Verfügung.[^1]

Ansible ist ebenfalls in Python geschrieben, was es leicht macht, es zu erweitern und anzupassen, um Ihren spezifischen Anforderungen gerecht zu werden.[^2]

>One of Ansible’s greatest strengths is its ability to run regular shell commands verbatim, so you
>can take existing scripts and commands and work on converting them into idempotent playbooks
>as time allows. For someone (like me) who was comfortable with the command line, but never
>became proficient in more complicated tools like Puppet or Chef (which both required at least a
>slight understanding of Ruby and/or a custom language just to get started)

**Quellen und Referenzen:**

[^1]: Gartner Automation Tools Review and Ratings [Retrieved from](https://www.gartner.com/reviews/market/continuous-configuration-automation-tools)
[^2]: Geerling, J. (2015). Ansible for DevOps. Leanpub. [Retrieved from](https://leanpub.com/ansible-for-devops)
[^3]: Red Hat Ansible Blog [Retrieved from](https://www.ansible.com/blog/)
[^4]: Puppet Labs Blog [Retrieved from](https://puppet.com/blog)
[^5]: Chef Blog [Retrieved from](https://blog.chef.io/)
[^6]: Ansible vs Puppet vs Chef: What are the differences? [Retrieved from](https://betterstack.com/community/comparisons/chef-vs-puppet-vs-ansible)
[^7]: Gartner Ansible Tower Reviews [Retrieved from](https://www.gartner.com/reviews/market/continuous-configuration-automation-tools/vendor/red_hat/product/ansible-tower?marketSeoName=continuous-configuration-automation-tools&vendorSeoName=red_hat&productSeoName=ansible-tower)
[^8]: Gartner Semaphore Reviews [Retrieved from](https://www.gartner.com/reviews/market/active-metadata-management/vendor/progress/product/semaphore)
[^9]: Was ist Ansible Semaphore [Retrieved from](https://github.com/ansible-semaphore/semaphore)
[^10]: Semaphore vs AWX [Retrieved from](https://www.netways.de/en/blog/2023/07/06/semaphore-rundeck-awx-ansible-gui/)
