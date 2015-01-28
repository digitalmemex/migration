migration
=========

track and replay DeepaMehta plugin based TopicType modifications

The aim of the migration plugin is the migration of plugin based TopicType changes from one DeepaMehta instance to another. In other words we want to record all changes applied to one instance and to deploy the tracked modifications into another instance.

#### questions

is this repo about recording
* changes to all type definitions (or really just about TopicType defs)?
* interactive changes by users to type definitions (which are not yet persisted in any plugins migration)
* does "modification" also include _creation_ of new type defs?

if so, i might  be interested in helping because of _users building apps_ and then i would say:

#### alternate intro

track and apply interactive changes made to any dm/x type definition

The aim of this plugin is the migration of a users changes to type definitions from one dm/x instance to another. In other words, we want to record all modifications to type definitions done by users in one dm/x instance and deploy these changes into another instance.

#### challenges

migrations can only be replayed by imperative code so, we either would need to generate some java code automatically here _or_ 
* define/develop/introduce a language which this plugin can understand and then realize being installed on another instance
* define all basic operations the exchange format/language must/should include
* hook into any modification made to any type definition with a server-side plugin (beginning after installation)
* read out index-mode uris, data type uri, label config, view config (icon), assoc defs - no problem

##### details ..
.. about the very first challenge: what operations would we need to track and how could we?
* track: creation or edit of any "Topic Type", "Association Type", "Aggregation Definition" or "Composition Definition"

##### how would a simple model/exchange format look like:
<pre>
{ operation: "OPERATION_NAME", body: { type_uri: "my.type.uri", data_type_uri : "dm4.core.text", index_mode_uris: ["dm4.core.key"]}, view_config: {}, label_config: ["my.type.uri1"], assoc_defs: [{}] }
</pre>


