# Exploring Timescale Cloud
Welcome to Timescale Cloud! Timescale Cloud is a cloud-native TimescaleDB as a
service that is easy to get started and powerful enough for the most demanding
scenarios. This tutorial walks you through setting up your Timescale Cloud
account and completing your first tutorial project.

### Create a Timescale Cloud account
Sign up for Timescale Cloud by visiting [console.cloud.timescale.com][cloud-signup].
Provide your full name, email address, and a strong password to start:

<img class="main-content__illustration" src="https://s3.amazonaws.com/assets.timescale.com/docs/images/tsc-signup.png" alt="Sign up for Timescale Cloud"/>

You need to confirm your account by clicking the link you receive by email.
If you do not receive this link, check your spam folder first, then
[contact us][contact-timescale].

### Create your first service
When you have completed account verification, visit the
[Timescale Cloud console][cloud-console] and login with your credentials.

To begin, click `Create database`.

<img class="main-content__illustration" src="https://s3.amazonaws.com/assets.timescale.com/docs/images/tsc-createdb.png" alt="Set up a Timescale Cloud service"/>

<highlight type="tip">
Don't worry too much about the size settings that you choose initially.
With Timescale Cloud, it's easy to modify both the compute (CPU/Memory) and
storage associated with the service that you just created. As you get to know
TimescaleDB and how your data processing needs vary, it's easy to
[right-size your service with a few clicks](/cloud/latest/scaling-a-service/)!
</highlight>

After you select `Create database`, you see confirmation of your service
account and password information. You should save the information in this
confirmation screen in a safe place:

<img class="main-content__illustration" src="https://s3.amazonaws.com/assets.timescale.com/docs/images/tsc-build-service.png" alt="View Timescale Cloud service information"/>

<highlight type="warning">
If you forget your password, you can reset it from the `Operations` menu in the service dashboard.
</highlight>

It takes a couple minutes for your service to be provisioned. When your
database is ready for connection, a green `Running` label shows above
the service in the service dashboard.

<img class="main-content__illustration" src="https://s3.amazonaws.com/assets.timescale.com/docs/images/tsc-service-dashboard.png" alt="View all Timescale Cloud services"/>

Select any service to view *service details*. You can obtain connection,
configuration, and utilization information. In addition, you can reset the
password for your service, power down or power up any service (which stops
or starts your compute, although your storage persists), or delete
a service altogether.

<img class="main-content__illustration" src="https://s3.amazonaws.com/assets.timescale.com/docs/images/tsc-running-service.png" alt="View Timescale Cloud service information"/>

### Rename your service
Your service is created with a name that is automatically generated. We
recommend that you rename your service to something more meaningful. To do this,
navigate to the `Service details` section for the service you want to rename,
and click the pencil icon next to the name. Type the new name for your service,
and click `Rename` to save the changes.

### Complete your first tutorial
Congratulations! You are now up and running with Timescale Cloud. To
familiarize yourself with the features and capabilities of the product, we
recommend that you complete the [Getting Started][getting-started] tutorial.

### Learn more about TimescaleDB
Read about TimescaleDB features in our documentation:

-   Create your first [hypertable][hypertable-info].
-   Run your first query using [time_bucket()][time-bucket-info].
-   Trying more advanced time-series functions, starting with
    [gap filling][gap-filling-info] or [real-time aggregates][aggregates-info].

### Keep testing during your free trial
You're now on your way to a great start with Timescale!

You have an unthrottled, 30-day free trial with Timescale Cloud to
continue to test your use case. Before the end of your trial, we encourage you
to add your credit card information. This ensures a smooth transition after
your trial period concludes.

### Summary
We're excited to play a small part in helping you build a best-in-class
time-series application or monitoring tool. If you have any questions, please
feel free to [join our community Slack group][slack-info]
or [contact us][contact-timescale] directly.

## Advanced configuration and multi-node setup
Timescale Cloud is a versatile hosting service that provides a growing list of
advanced features for your PostgreSQL and time-series data workloads.

For additional documentation on how to:
*   [Resize compute and storage][resize] at any time
*   [Customize your database configuration][configuration] easily
*   [Create a TimescaleDB multi-node cluster][multi-node] in Timescale Cloud

[cloud-signup]: https://console.cloud.timescale.com
[slack-info]: https://slack-login.timescale.com
[getting-started]: /timescaledb/latest/getting-started/
[cloud-console]: https://console.cloud.timescale.com/login
[contact-timescale]: https://www.timescale.com/contact
[hypertable-info]: /timescaledb/latest/how-to-guides/hypertables
[time-bucket-info]: /timescaledb/latest/how-to-guides/query-data/advanced-analytic-queries#time-bucket
[gap-filling-info]: /timescaledb/latest/how-to-guides/query-data/advanced-analytic-queries#gap-filling
[aggregates-info]: /timescaledb/latest/getting-started/create-cagg
[resize]: /scaling-a-service/
[configuration]: /customize-configuration/
[multi-node]: /cloud-multi-node/
