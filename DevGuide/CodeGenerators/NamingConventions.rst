Naming conventions
------------------

*General conventions :*

- les noms de Types commencent par des majuscules
- les noms d'instance commencent par des minuscules
- les noms des ports commences par des préfixes in ou out.
- ... ??

*ROS conventions :*

According ROS, the naming convention topic (http://www.ros.org/wiki/Naming) says:

- Topic and service names live in a hierarchical namespace, and client libraries provide mechanisms for remapping them at runtime, so there is more flexibility than with packages. However, it's best to minimize the need for namespacing and name remapping.
- Topic and service names should follow common C variable naming conventions: lower case, with underscore separators, e.g. laser_scan
- Topic and service names should be reasonably descriptive. If a planner node publishes a message containing its current state, the associated topic should be called planner_state, not just state. »

/Robot/Composant/Suffixe

With "Robot" and "Component" and "Suffix" names consist of alphanumeric characters respecting the naming convention C.
ie. alpha = [a-z0-9] without "-" or "." with "_"
eg. for a sensor on a camera WIFIBOT: / WIFIBOT / camera / image_raw

TBD
