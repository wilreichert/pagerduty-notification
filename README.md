Use this [notification](http://rundeck.org/docs/developer/notification-plugin-development.html)
plugin to send [trigger](http://developer.pagerduty.com/documentation/integration/events/trigger)
events to your [PagerDuty](https://pagerduty.com) service.

The plugin requires one parameter:

* subject: This string will be set as the description for the generated incident.

Context variables usable in the subject line:

* `${job.status}`: Job execution status (eg, FAILED, SUCCESS).
* `${job.project}`: Job project name.
* `${job.name}`: Job name.
* `${job.group}`: Job group name.
* `${job.user}`: User that executed the job.
* `${job.execid}`: Job execution ID.

## Installation

Copy the groovy script to the plugins directory:

    cp src/PagerDutyNotification.groovy to $RDECK_BASE/libext

and start using it!

## Configuration

The plugin requires one configuration entry.

* service_key: This is the API Key to your service.

Configure the service_key in your project configuration by
adding an entry like so: $RDECK_BASE/projects/{project}/etc/project.properties

    project.plugin.Notification.PagerDutyNotification.service_key=xx123049e89dd45f28ce35467a08577yz

Or configure it at the instance level: $RDECK_BASE/etc/framework.properties

    framework.plugin.Notification.PagerDutyNotification.service_key=xx123049e89dd45f28ce35467a08577yz

