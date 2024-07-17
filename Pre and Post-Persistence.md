**PRE AND POST PRESISTENCE HOOKS DOCUMENTATION:**

**Pre-persistence hooks:**

-   Pre-persistence hooks are methods that are called before an entity
    is persisted, updated, or deleted in the database. These hooks
    provide an opportunity to perform additional processing, validation,
    or transformation on the data before it is persisted.

**Post-persistence hooks:**

-   Post-persistence hooks are methods that are called after an entity
    has been persisted, updated, or deleted in the database. These hooks
    provide an opportunity to perform additional processing,
    notification, or indexing on the data after it has been persisted.

**\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--**

**LIST OF PRE AND POST PERSISTANCE HOOKS:**

1.  **POST_SAVE_SCHEDULER_TASK:**

-   This post-persist hook is triggered after a rule is created,
    modified, or deleted. Its purpose is to save a scheduler task that
    will run the scheduler based on the rule.

**Configuration:**

-   orderOfExecution: 1 - This specifies the order in which this hook
    should be executed. In this case, it\'s the first hook to be
    executed.

-   jobOperationTypes: \[\"CREATED\", \"MODIFIED\", \"DELETED\"\] - This
    specifies the types of operations that will trigger this hook. In
    this case, the hook will be executed when a rule is created,
    modified, or deleted.

-   type: \"POST_SAVE_SCHEDULER_TASK\" - This is the type of
    post-persist hook. In this case, it\'s a custom hook that saves a
    scheduler task.

-   configurationJobInstanceId: \"\" - This field is empty.

-   shouldChildrenInheritPersistHook: false - This specifies whether
    child objects should inherit this post-persist hook. In this case,
    it\'s set to false, which means child objects will not inherit this
    hook.

**Overview Of the Process:**

-   A rule is created, modified, or deleted.

-   The POST_SAVE_SCHEDULER_TASK post-persist hook is triggered.

-   The hook saves a scheduler task that will run the scheduler based on
    the rule.

-   The scheduler task is executed, which runs the scheduler according
    to the updated rule.

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

2.  **PRE_SUBJOB_ASSOCIATION:**

-   This pre-persist hook is triggered before a job instance is saved.
    Its purpose is to identify the parent job instance based on the
    parent job type and parent job identifier, and establish the
    association between the subjob and the parent job.

**Configuration:**

1.  orderOfExecution: 2 - This specifies the order in which this hook
    should be executed. In this case, it\'s the second hook to be
    executed.

2.  type: \"PRE_SUBJOB_ASSOCIATION\" - This is the type of pre-persist
    hook. In this case, it\'s a custom hook that establishes the
    association between a subjob and its parent job.

3.  configurationJobInstanceId: \"\" - This field is empty

**Overview Of the Process:**

-   A job instance is about to be saved.

-   The PRE_SUBJOB_ASSOCIATION pre-persist hook is triggered.

-   The hook identifies the parent job instance based on the parent job
    type and parent job identifier.

-   The hook establishes the association between the subjob and the
    parent job instance.

-   The job instance is saved with the established association.

  \-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

3.  **PRE_GENERATE_LINK_URL:**

-   This pre-persist hook is triggered before a job instance is saved.
    Its purpose is to generate a hyperlink URL that links a field (e.g.,
    Policy Number) in the Claims module (MIS view) to the corresponding
    policy job in edit mode.

**Configuration:**

-   orderOfExecution: 1 - This specifies the order in which this hook
    should be executed. In this case, it\'s the first hook to be
    executed.

-   type: \"PRE_GENERATE_LINK_URL\" - This is the type of pre-persist
    hook. In this case, it\'s a custom hook that generates a hyperlink
    URL.

**Work Flow:**

-   A job instance is about to be saved.

-   The PRE_GENERATE_LINK_URL pre-persist hook is triggered.

-   The hook checks the configuration for LinkURL fields (e.g., Policy
    Number).

-   The hook generates a hyperlink URL linking the field to the
    corresponding policy job in edit mode.

-   The generated link value is stored in a hidden field.

-   The job instance is saved with the generated link value.

> \-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

4.  **PRE_GENERATE_TATS:**

-   This pre-persist hook is triggered before a job instance is saved.
    Its purpose is to generate TATS (Temporary Application Transactional
    Storage) values for an instance during creation, update, or status
    change.

**Configuration:**

-   orderOfExecution: 1 - This specifies the order in which this hook
    should be executed. In this case, it\'s the first hook to be
    executed.

-   type: \"PRE_GENERATE_TATS\" - This is the type of pre-persist hook.
    In this case, it\'s a custom hook that generates TATS values.

**Work Flow:**

When a job instance is about to be saved, this pre-persist hook is
triggered. The hook will then generate TATS values based on three types
of calculations:

1)  Date Field Differences:

    a.  The hook calculates the difference between two date fields.

2)  Field Calculations (BODMAS rule):

    a.  The hook performs calculations between two or more fields,
        following the BODMAS (Brackets, Orders, Division,
        Multiplication, Addition, and Subtraction) rule.

3)  Global Report Calculations:

    a.  The hook calculates a field value from all sub-type instances of
        a parent instance. This is useful for generating global reports
        that aggregate data from multiple instances.

**Overview Of the Process:**

-   A job instance is about to be saved.

-   The PRE_GENERATE_TATS pre-persist hook is triggered.

-   The hook generates TATS values based on date field differences,
    field calculations, and global report calculations.

-   The generated TATS values are stored.

-   The job instance is saved with the generated TATS values.

  \-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

5.  **POST_GENERATE_PARENT_TATS:**

- This post-persist hook is triggered after a sub-instance is created,
updated, or deleted. Its purpose is to generate TATS (Temporary
Application Transactional Storage) values for the parent job instance.

**Configuration:**

-   orderOfExecution: 1 - This specifies the order in which this hook
    should be executed. In this case, it\'s the first hook to be
    executed.

-   jobOperationTypes: \[\"CREATED\", \"MODIFIED\", \"DELETED\"\] - This
    specifies the types of job operations that trigger this hook. In
    this case, the hook is triggered when a sub-instance is created,
    updated, or deleted.

-   type: \"POST_GENERATE_PARENT_TATS\" - This is the type of
    post-persist hook. In this case, it\'s a custom hook that generates
    parent job instance TATS values.

-   configurationJobInstanceId: \"\" - This field is empty.

-   shouldChildrenInheritPersistHook: false - This flag indicates that
    child instances should not inherit this post-persist hook.

**Work Flow:**

When a sub-instance is created, updated, or deleted, this post-persist
hook is triggered. The hook will then generate TATS values for the
parent job instance.

**Overview Of the Process:**

-   A sub-instance is created, updated, or deleted.

-   The POST_GENERATE_PARENT_TATS post-persist hook is triggered.

-   The hook generates TATS values for the parent job instance.

-   The generated TATS values are stored.

-   The parent job instance is updated with the new TATS values.

> \-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

6.  **AUTO_FIELD_VALUE_GENERATION:**

- This pre-persist hook is triggered before a job instance is saved. Its
purpose is to automatically generate field values for an instance.

**Configuration:**

-   orderOfExecution: 1 - This specifies the order in which this hook
    should be executed. In this case, it\'s the first hook to be
    executed.

-   type: \"AUTO_FIELD_VALUE_GENERATION\" - This is the type of
    pre-persist hook. In this case, it\'s a custom hook that generates
    field values.

**Work Flow:**

When a job instance is about to be saved, this pre-persist hook is
triggered. The hook will then generate field values based on two types
of generation methods:

1.  Default Generation Type

The hook uses a default generation method to populate field values. This
method is likely based on predefined rules or algorithms.

2.  Custom Logic

The hook uses custom logic to generate field values. This custom logic
is specific to certain clients or systems, such as:

i.  JCG

ii. Indinfravit

This custom logic may involve complex calculations, data
transformations, or integrations with external systems.

**Overview Of the Process:**

-   A job instance is about to be saved.

-   The AUTO_FIELD_VALUE_GENERATION pre-persist hook is triggered.

-   The hook generates field values using default generation type or
    custom logic (JCG,Indinfravit).

-   The generated field values are populated in the job instance.

-   The job instance is saved with the generated field values.

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

7.  **POST_AUTO_USER_CREATION:**

- This post-persist hook is triggered after a job instance is created. Its
purpose is to automatically create a user account associated with the
instance.

**Configuration:**

-   orderOfExecution: 1 - This specifies the order in which this hook
    should be executed. In this case, it\'s the first hook to be
    executed.

-   jobOperationTypes: null

-   type: \"POST_AUTO_USER_CREATION\" - This is the type of post-persist
    hook. In this case, it\'s a custom hook that creates a user account.

-   configurationJobInstanceId: \"\<configurationJobInstanceId\>\" -
    This specifies the job instance ID that contains the configuration
    for user creation. This instance likely stores the required details
    for user creation, such as role name, password, and other settings.

-   shouldChildrenInheritPersistHook: false - This flag indicates that
    child instances should not inherit this post-persist hook.

**Overview Of the Process:**

When a job instance is created, this post-persist hook is triggered. The
hook will then create a user account associated with the instance.

-   The hook retrieves the user\'s email address from a configured field
    in the job instance.

-   The hook uses the configuration stored in the
    configurationJobInstanceId instance to retrieve the required details
    for user creation, such as:

1)  Role name

2)  Password

3)  Other required fields in configuration.

-   The hook creates a new user account with the retrieved email address
    and configured details.

-   The user account is saved and associated with the job instance.

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

8.  **POST_AUTO_USER_DELETION:**

- This post-persist hook is triggered after a job instance is deleted. Its
purpose is to automatically delete the user account associated with the
instance.

**Configuration:**

-   orderOfExecution: 1 - This specifies the order in which this hook
    should be executed. In this case, it\'s the first hook to be
    executed.

-   jobOperationTypes: null

-   type: \"POST_AUTO_USER_DELETION\" - This is the type of post-persist
    hook. In this case, it\'s a custom hook that deletes a user account.

-   configurationJobInstanceId: \"\<configurationJobInstanceId\>\" -
    This specifies the job instance ID that contains the configuration
    for user deletion. This instance likely stores the required details
    for user deletion, such as the user\'s email address.

-   shouldChildrenInheritPersistHook: false - This flag indicates that
    child instances should not inherit this post-persist hook.

**Work Flow:**

When a job instance is deleted, this post-persist hook is triggered. The
hook will then delete the user account associated with the instance.
Here\'s how it works:

-   The hook retrieves the user\'s email address from a configured field
    in the configurationJobInstanceId instance. This is the same
    instance that was used to create the user account.

-   The hook uses the retrieved email address to identify the user
    account to be deleted.

-   The hook deletes the user account associated with the email address.

-   The user account is removed from the system.

> \-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

9.  **POST_SEND_EMAIL:**

- This post-persist hook is triggered after a job instance is created or
its status changes. Its purpose is to send an email notification to
stakeholders and create a communication history sub-instance.

**Configuration:**

-   orderOfExecution: 1 - This specifies the order in which this hook
    should be executed. In this case, it\'s the first hook to be
    executed.

-   type: \"POST_SEND_EMAIL\" - This is the type of post-persist hook.
    In this case, it\'s a custom hook that sends an email notification.

**Work Flow:**

When a job instance is created or its status changes, this post-persist
hook is triggered. The hook will then send an email notification and
create a communication history sub-instance.

-   The hook retrieves the Email Notification template configured on the
    target workflow step.

-   The hook reads the following fields from the template:

1)  From Email

2)  To

3)  CC

4)  Subject

5)  Body

-   The hook replaces any placeholders or fields in the template with
    actual data from the job instance.

-   The hook sends the email notification to the specified recipients.

-   After sending the email, the hook creates a new sub-instance of the
    job instance, specifically for communication history (with a jobType
    of \"Communication history\").

-   The sub-instance is created to store a record of the email
    notification sent.

    \-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

10. **POST_CAMPAIGN_SAVE_SCHEDULER_TASK:**

- This post-persist hook is triggered after a job instance is created,
modified, or deleted. Its purpose is to save, update, or delete campaign
instance data in the scheduler database, which is used to trigger
campaign email sending tasks.

**Configuration:**

-   orderOfExecution: 1 - This specifies the order in which this hook
    should be executed. In this case, it\'s the first hook to be
    executed.

-   jobOperationTypes: \[\"CREATED\", \"MODIFIED\", \"DELETED\"\] - This
    specifies the job operation types that trigger this hook. In this
    case, the hook is triggered when a job instance is created,
    modified, or deleted.

-   type: \"POST_CAMPAIGN_SAVE_SCHEDULER_TASK\" - This is the type of
    post-persist hook. In this case, it\'s a custom hook that saves,
    updates, or deletes campaign instance data in the scheduler
    database.

-   configurationJobInstanceId: \"\" - This field is empty, indicating
    that the hook doesn\'t rely on a specific job instance ID for
    configuration.

-   shouldChildrenInheritPersistHook: false - This flag indicates that
    child instances should not inherit this post-persist hook.

**Work Flow:**

When a job instance is created, modified, or deleted, this post-persist
hook is triggered. The hook will then save, update, or delete the
campaign instance data in the scheduler database.

-   The hook retrieves the campaign instance data from the job instance.

-   Based on the job operation type, the hook performs one of the
    following actions:

1)  CREATED: Saves the campaign instance data in the scheduler database.

2)  MODIFIED: Updates the campaign instance data in the scheduler
    database.

3)  DELETED: Deletes the campaign instance data from the scheduler
    database.

-   The scheduler database is updated with the latest campaign instance
    data.

-   The scheduler uses this data to trigger campaign email sending
    tasks.

> \-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

11. **POST_FETCH_RFP_DOCUMENTS:**

- This post-persist hook is triggered after a job instance is created,
modified, or deleted. Its purpose is to retrieve all RFP documents for a
given SolNumber, upload them to S3, and save the S3 file URLs as
sub-jobs of the instance.

**Configuration:**

-   orderOfExecution: 1 - This specifies the order in which this hook
    should be executed. In this case, it\'s the first hook to be
    executed.

-   jobOperationTypes: \[\"CREATED\", \"MODIFIED\", \"DELETED\"\] - This
    specifies the job operation types that trigger this hook. In this
    case, the hook is triggered when a job instance is created,
    modified, or deleted.

-   type: \"POST_FETCH_RFP_DOCUMENTS\" - This is the type of
    post-persist hook. In this case, it\'s a custom hook that retrieves
    RFP documents and uploads them to S3.

-   configurationJobInstanceId: \"\<configurationJobInstanceId\>\" -
    This specifies the ID of the configuration job instance that
    provides the necessary information for the hook to function. This
    includes the field name, sub-job type, and other required details.

-   shouldChildrenInheritPersistHook: false - This flag indicates that
    child instances should not inherit this post-persist hook.

**Work Flow:**

When a job instance is created, modified, or deleted, this post-persist
hook is triggered. The hook will then retrieve all RFP documents for the
given SolNumber and upload them to S3.

-   The hook retrieves the SolNumber from the job instance.

-   The hook uses the SolNumber to fetch all RFP documents associated
    with it.

-   The hook uploads the retrieved documents to S3.

-   The hook saves the S3 file URLs as sub-jobs of the instance.

-   The sub-jobs are created with the necessary information, such as the
    field name and sub-job type, which are retrieved from the
    configuration job instance.

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

12. **POST_CREATE_INSTANCE_FROM_XLSX:**

- This post-persist hook is triggered after a job instance is created in
the \"Mail Repository\" job type. Its purpose is to create a new job
instance by parsing an XLSX file, validate the data, and update the XLSX
file with any errors found.

**Configuration:**

-   orderOfExecution: 1 - This specifies the order in which this hook
    should be executed. In this case, it\'s the first hook to be
    executed.

-   jobOperationTypes: \[\"CREATED\"\] - This specifies the job
    operation type that triggers this hook. In this case, the hook is
    triggered when a job instance is created.

-   type: \"POST_CREATE_INSTANCE_FROM_XLSX\" - This is the type of
    post-persist hook. In this case, it\'s a custom hook that creates a
    job instance from an XLSX file.

-   configurationJobInstanceId: \"\<configurationJobInstanceId\>\" -
    This specifies the ID of the configuration job instance that
    provides the necessary information for the hook to function. This
    includes the job type, field name, table structures, and add-more
    fields.

-   shouldChildrenInheritPersistHook: false - This flag indicates that
    child instances should not inherit this post-persist hook.

**Work Flow:**

When a job instance is created in the \"Mail Repository\" job type, this
post-persist hook is triggered. The hook will then create a new job
instance by parsing the XLSX file, validate the data, and update the
XLSX file with any errors found.

-   The hook retrieves the XLSX file from the job instance.

-   The hook parses the XLSX file to extract the necessary data.

-   The hook uses the configuration job instance to identify the job
    type, field name, table structures, and add-more fields.

-   The hook validates the data extracted from the XLSX file. If any
    empty field values are found, the hook replaces the cell with a
    yellow color.

-   After all validations, the hook saves the updated XLSX file to the
    instance.

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

13. **POST_CHATGPT_PARSING:**

- This post-persist hook is triggered after a job instance is created. Its
purpose is to create a data JSON for a specific job type using ChatGPT
and save it in a job instance for the \"datasetAI\" job type. The hook
uses a configured job instance to map the keys from which the
information is extracted to provide the values.

**Configuration:**

-   orderOfExecution: 1 - This specifies the order in which this hook
    should be executed. In this case, it\'s the first hook to be
    executed.

-   type: \"POST_CHATGPT_PARSING\" - This is the type of post-persist
    hook. In this case, it\'s a custom hook that creates a data JSON
    using ChatGPT.

-   configurationJobInstanceId: \"\<configurationJobInstanceId\>\" -
    This specifies the ID of the configuration job instance that
    provides the necessary information for the hook to function. This
    includes the mapping keys for extracting data from the job instance.

-   shouldChildrenInheritPersistHook: false - This flag indicates that
    child instances should not inherit this post-persist hook.

**Work Flow:**

When a job instance is created, this post-persist hook is triggered. The
hook will then create a data JSON for the specific job type using
ChatGPT and save it in a job instance for the \"datasetAI\" job type.

-   Retrieves the configured job instance using the
    configurationJobInstanceId.

-   Uses the configured job instance to map the keys from which the
    information is extracted.

-   Creates a data JSON for the \"datasetAI\" job type using ChatGPT.

-   Parses the attachments and includes them in the data JSON.

-   Saves the created data JSON in the job instance.

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

14. **POST_API_ON_STATUS_CHANGE**:

- This post-persist hook is triggered after an instance\'s status changes.
Its purpose is to perform various actions based on the status change,
such as updating the status of parent or subjobs, or modifying the
status of subjobs when they are moved or copied to a different parent
instance.

**Configuration**

-   orderOfExecution: 1 - This specifies the order in which this hook
    should be executed. In this case, it\'s the first hook to be
    executed.

-   type: \"POST_API_ON_STATUS_CHANGE\" - This is the type of
    post-persist hook. In this case, it\'s a custom hook that performs
    actions based on instance status changes.

-   shouldChildrenInheritPersistHook: false - This flag indicates that
    child instances should not inherit this post-persist hook.

**Work Flow:**

When an instance\'s status changes, this post-persist hook is triggered.
The hook can perform various actions, including:

-   Updating the status of the parent instance

-   Changing the status of subjobs

-   Updating the status of subjobs when they are moved to a different
    parent instance

-   Changing the status of subjobs when they are copied to a different
    parent instance

-   This hook provides a flexible way to automate various workflows
    based on instance status changes.

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

15. **POST_CREATE_TICKET_FROM_MAIL:**

- This post-persist hook is triggered after a \"Mail\" instance is
created. Its purpose is to automatically create a \"Ticket\" instance
and a \"Mail Repository\" subjob, which is linked to the newly created
ticket.

**Configuration:**

-   orderOfExecution: 1 - This specifies the order in which this hook
    should be executed. In this case, it\'s the first hook to be
    executed.

-   jobOperationTypes: null

-   type: \"POST_CREATE_TICKET_FROM_MAIL\" - This is the type of
    post-persist hook. In this case, it\'s a custom hook that creates a
    ticket and mail repository from a mail instance.

-   retrievalFieldsFromResponse: null

-   actionOnRetrievalFields: null

-   configurationJobInstanceId: null

-   shouldChildrenInheritPersistHook: false - This flag indicates that
    child instances should not inherit this post-persist hook.

**Work Flow:**

When a \"Mail\" instance is created, this post-persist hook is
triggered. The hook performs the following actions:

-   Creates a new \"Ticket\" instance.

-   Creates a new \"Mail Repository\" subjob, which is linked to the
    newly created ticket.

-   Links the mail instance to the newly created ticket and mail
    repository.

-   This hook automates the process of creating tickets and mail
    repositories from mail instances, streamlining the workflow and
    reducing manual effort.

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

16. **POST_JOB_INSTANCE_VALIDATION: **

- This post-persist hook is triggered after a job instance is created. Its
purpose is to validate the completeness of the created instance and
trigger an email notification if the job type is configured to do so.

**Configuration**

-   orderOfExecution: 1 - This specifies the order in which this hook
    should be executed. In this case, it\'s the first hook to be
    executed.

-   type: \"POST_JOB_INSTANCE_VALIDATION\" - This is the type of
    post-persist hook. In this case, it\'s a custom hook that validates
    the completeness of a job instance and triggers an email
    notification if necessary.

-   configurationJobInstanceId: \"\<configurationJobInstanceId\>\" -
    This specifies the ID of the configuration job instance that
    contains the necessary information for the email notification.

-   shouldChildrenInheritPersistHook: false - This flag indicates that
    child instances should not inherit this post-persist hook.

**Work Flow:**

When a job instance is created, this post-persist hook is triggered. The
hook performs the following actions:

-   Validates the completeness of the created job instance.

-   If the job type is configured to send an email notification (i.e.,
    \"sendMail\" is set as the response), the hook triggers an email
    notification.

-   The email notification is sent using either Outlook or Gmail,
    depending on the configuration.

-   The configuration instance is used to retrieve the necessary
    information for the email notification, such as the reply mail\'s
    body and any specific required fields that need to be validated.

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

17. **POST_PUBLIC_DATA_ACCESS:**

- The POST_PUBLIC_DATA_ACCESS post-persist hook is triggered after a job
instance is created. Its purpose is to create an instance in the
accessible-api-service that can be accessed publicly.

**Configuration**

-   orderOfExecution: 1 - This specifies the order in which this hook
    should be executed. In this case, it\'s the first hook to be
    executed.

-   type: \"POST_PUBLIC_DATA_ACCESS\" - This is the type of post-persist
    hook. In this case, it\'s a custom hook that creates a publicly
    accessible instance in the accessible-api-service.

-   shouldChildrenInheritPersistHook: false - This flag indicates that
    child instances should not inherit this post-persist hook.

**Work Flow:**

When a job instance is created, this post-persist hook is triggered. The
hook creates an instance in the accessible-api-service that can be
accessed publicly. This allows external systems or users to access the
instance data without requiring authentication or authorization.

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

18. **POST_SAVE_JOBINSTANCE_CONDITIONS**

- The POST_SAVE_JOBINSTANCE_CONDITIONS post-persist hook is triggered
after a job instance is saved. Its purpose is to extract a special
filter JSON from the job instance data and save it in a structured
format in the condition's parameter of the job instance.

**Configuration:**

-   orderOfExecution: 1 - This specifies the order in which this hook
    should be executed. In this case, it\'s the first hook to be
    executed.

-   type: \"POST_SAVE_JOBINSTANCE_CONDITIONS\" - This is the type of
    post-persist hook. In this case, it\'s a custom hook that saves the
    special filter JSON in a structured format.

-   configurationJobInstanceId: \"\<configurationJobInstanceId\>\" -
    This specifies the ID of the configuration job instance that
    contains the necessary information for extracting the special filter
    JSON.

-   shouldChildrenInheritPersistHook: false - This flag indicates that
    child instances should not inherit this post-persist hook.

**Work Flow:**

When a job instance is saved, this post-persist hook is triggered. The
hook performs the following actions:

-   Retrieves the special filter JSON from the job instance data using
    the configurationJobInstanceId to determine the correct field name.

-   Extracts the relevant information from the special filter JSON.

-   Saves the Extracted information in a structured format in the
    condition's parameter of the job instance.

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

19. **POST_RETRIEVE_MAIL_TYPE:**

- The POST_RETRIEVE_MAIL_TYPE post-persist hook is triggered after a job
instance is retrieved. Its purpose is to determine the type of mail,
either from ChatGPT or from the configuration of the \"Mail Repository\"
job type, and set the type of mail in a data field in the Mail
Repository\'s instance.

**Configuration:**

-   orderOfExecution: 1 - This specifies the order in which this hook
    should be executed. In this case, it\'s the first hook to be
    executed.

-   type: \"POST_RETRIEVE_MAIL_TYPE\" - This is the type of post-persist
    hook. In this case, it\'s a custom hook that retrieves the mail
    type.

-   shouldChildrenInheritPersistHook: false - This flag indicates that
    child instances should not inherit this post-persist hook.

**Work Flow:**

When a job instance is retrieved, this post-persist hook is triggered.
The hook performs the following actions:

-   Checks if the mail type is specified in the ChatGPT response. If it
    is, the hook retrieves the mail type from the ChatGPT response.

-   If the mail type is not specified in the ChatGPT response, the hook
    retrieves the mail type from the configuration of the \"Mail
    Repository\" job type.

-   Sets the retrieved mail type in a data field in the Mail
    Repository\'s instance.

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--
