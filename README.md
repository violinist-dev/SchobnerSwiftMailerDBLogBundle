# SchobnerSwiftMailerDBLogBundle
Persist email sendet with SwiftMailer to database.

# (This is a early alpha Version. Don't use it productive)

# Install:

```composer require schobner/swift-mailer-db-log```

### Config:
app/AppKernel.php anpassen:

```
class AppKernel extends Kernel
{

    public function registerBundles()
    {
        $bundles = [
            new Schobner\SwiftMailerDBLogBundle\SchobnerSwiftMailerDBLogBundle(),
        ];

```
Set config:
```
schobner_swift_mailer_db_log:
    email_log_entity: AppBundle\Entity\EmailLog
```

### Extend class:
All db settings will be automatically set
```
namespace AppBundle\Entity;

use Schobner\SwiftMailerDBLogBundle\Model\EmailLog as BaseEmailLog;

/**
 * @ORM\Entity()
 * @ORM\Table(name="swift_mailer_log")
 */
class EmailLog extends BaseEmailLog
{
    // ... add your logic if required ...
}

```
