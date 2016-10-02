# Database Design

The Open Journal Systems 2.x database design is flexible, comprehensive, and consistent; however, owing to the number of features and options the system offers, it is also fairly broad in its scope.

For further information, please see ``dbscripts/xml/ojs_schema.xml``.

**Table 2.1. OJS Database Schema**

| Table Name | Primary Key | Description |
| ----- | ----- | ----- |
| ``access_keys`` | ``access_key_id`` | Stores keys for one-click reviewer access |
| ``article_authors`` | ``author_id`` | Stores article authors on a per-article basis |
| ``article_comments`` | ``comment_id`` | Stores comments between members of the article editing process; note that this is not used for reader comments |
| ``article_email_log`` | ``log_id`` | Stores log entries describing emails that have been sent with regard to a specific article |
| ``article_event_log`` | ``log_id`` | Stores log entries describing events that have taken place with regard to a specific article |
| ``article_files`` | ``file_id, revision`` | Stores information regarding the various files (e.g. images, galleys, supplementary files) associated with a particular article |
| ``article_galleys`` | ``galley_id`` | Stores information about a particular layout (or “galley") associated with a particular article |
| ``article_html_galley_images`` | ``galley_id``, ``file_id`` | Associates images with galleys stored in the ``article_galleys`` table | 
| ``article_notes`` | ``note_id`` | Stores notes made for tracking purposes about a particular article by the editor(s) | 
| ``article_search_object_keywords`` | ``object_id``, ``pos`` | Provides an index associating keywords, by position, with search objects they appear in |
| ``article_search_objects`` | ``object_id`` | Lists search “objects", or entities that can be searched. |
| ``article_search_keyword_list`` | ``keyword_id`` | Stores all keywords appearing in items the system has indexed |
| ``article_supplementary_files`` | ``supp_id`` | Stores information about supplementary files belonging to a particular article |
| ``articles`` | ``article_id`` | Stores information on every submission in the system |
| ``comments`` | ``comment_id`` | Stores reader comments about articles |
| ``copyed_assignments`` | ``copyed_id`` | Stores information about copy editor assignments |
| ``currencies`` | ``currency_id`` | Stores information about currencies available to the subscription subsystem |
| ``custom_section_orders`` | ``issue_id``, ``section_id`` | Stores information about issue-specific ordering of journal sections |
| ``edit_assignments`` | ``edit_id`` | Stores information on editing assignments | 
| ``edit_decisions`` | ``edit_decision_id`` | Stores editor decisions with regard to a particular article | 
| ``email_templates`` | ``email_id`` | Stores a list of email templates that have been modified by the journal manager | 
| ``email_templates_data`` | ``email_id``, ``locale``, ``journal_id`` | Stores locale-specific text for emails in ``email_templates`` that have been modified by the journal manager | 
| ``email_templates_default`` | ``email_id`` | Stores a list of default email templates shipped with this version of OJS 2.x |
| ``email_templates_default_data`` | ``email_id``, ``locale``, ``journal_​id`` | Stores locale-specific text for emails in ``email_templates_default`` that shipped with this version of OJS 2.x |
| ``group_memberships`` |`` user_id``, ``group_id`` | Stores membership information for groups | 
| ``groups`` | ``group_id`` | Stores information about groups (a.k.a. custom masthead) | 
| ``issues`` | ``issue_id`` | Stores information about particular issues of hosted journals |
| ``journal_settings`` | ``journal_id``, ``setting_name`` | Provides a means of storing arbitrary-type settings for each journal | 
| ``journals`` | ``journal_id`` | Stores a list of hosted journals and a small amount of metadata. (Most metadata is stored in ``journal_settings``) |
| ``layouted_assignments`` | ``layouted_id`` | Stores information about layout editor assignments |
| ``notification_status`` | ``journal_id``, ``user_id`` | If a user wishes to be notified about a particular journal, they are associated with the journal ID in this table |
| ``oai_resumption_tokens`` | ``token`` | Contains resumption tokens for the OAI protocol interface |
| ``plugin_settings`` | ``plugin_name``, ``journal_id``, ``setting_name`` | Stores settings for individual plugins |
| ``proof_assignments`` | ``proof_id`` | Stores information about proofreading assignments | 
| ``published_articles`` | ``pub_id`` |When an article is published, an entry in this table is created to augment information in the ``articles`` table |
| ``review_assignments`` | ``review_id`` | Stores information about reviewer assignments | 
| ``review_rounds`` | ``article_id``, ``round`` | Associates an article ID with a review file revision for each round of review | 
| ``roles`` | ``journal_id``, ``role_id``, ``user_id`` | Defines what roles (manager, editor, reviewer, ...) users have within particular journals |
| ``rt_contexts`` | ``context_id`` | Reading Tools contexts |
| ``rt_searches`` | ``search_id`` | Reading Tools searches |
| ``rt_settings`` | ``journal_id`` | Reading Tools settings for each journal |
| ``rt_versions`` | ``version_id`` | Reading Tool versions |
| ``scheduled_tasks`` | ``class_name`` | On systems supporting scheduled tasks, this table is used by the task execution script to store information about when tasks were last performed |
| ``section_editors`` | ``journal_id``, ``section_id``, ``user_id`` | Associates section editors with sections of journals that they edit |
| ``sections`` | ``section_id`` | Defines sections within which journals can publish articles |
| ``sessions`` | ``session_id`` | Stores session information for the users who are currently using the system | 
| ``site`` | ``title`` | Stores site-wide configuration information |
| ``subscription_types`` | ``type_id`` | Defines types of subscriptions made available by the subscription subsystem | 
| ``subscriptions`` | ``subscription_id`` | Describes subscriptions “owned" by the system's users |
| ``temporary_files`` | ``file_id`` | Used for situations in which a file must be temporarily stored on the server between user requests |
| ``users`` | ``user_id`` | Stores information about every user registered with the system |
| ``versions`` | ``major``, ``minor``, ``revision``, ``build`` | Stores information about the current deployment of OJS 2.x |

