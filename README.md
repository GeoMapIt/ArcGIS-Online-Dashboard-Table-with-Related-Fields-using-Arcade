# ArcGIS Online Dashboard Table with Related Fields using Arcade

ArcGIS Online doesn't currently have a way where fields from related layers can be referenced in tool configs.
This Arcade script is used to attach specified (or all) fields from a related layer to another.
In this example I have a project point feature layer and a related submittal table layer. 
Each submittal is 1-1 related with a project. These related fields can be used by Dashboard tools.
This should work for any of ESRI's other products (where arcade data layer expressions are allowed).

To accomplish this, the script does the following:
  - Obtains all fields from Projects and Submittals (these are filtered to just the fields I need)
  - Iterates through submittals. Storing attribute information for submittals and each of their related projects. (attributes also filtered to fields above)
  - Formats the fields and attributes into a JSON string
  - Uses the JSON string to return a FeatureSet
