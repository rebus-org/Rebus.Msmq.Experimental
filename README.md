# Rebus.Msmq.Experimental

[![install from nuget](https://img.shields.io/nuget/v/Rebus.Msmq.Experimental.svg?style=flat-square)](https://www.nuget.org/packages/Rebus.Msmq.Experimental)

Provides a Microsoft Message Queue transport for [Rebus](https://github.com/rebus-org/Rebus) based on the [Experimental.System.Messaging](https://www.nuget.org/packages/Experimental.System.Messaging/) NuGet package.

![](https://raw.githubusercontent.com/rebus-org/Rebus/master/artwork/little_rebusbus2_copy-200x200.png)

---

NOTE THAT THIS PACKAGE IS BASED ON [Experimental.System.Messaging](https://www.nuget.org/packages/Experimental.System.Messaging/), which is NOT Microsoft's official MSMQ driver.

🤠

The reason for this package to exist, is because Microsoft chose to abandon the entire `System.Messaging` namespace when they ported code to .NET Core.

You can read more in [this GitHub issue: 'Add support for SystemMessaging and SOAP Web Services'](https://github.com/dotnet/runtime/issues/16409).

### Are there differences between this transport and [Rebus' real MSMQ transport](https://github.com/rebus-org/Rebus.Msmq)?

YES! First off, this package is based on an experimental port of the code from full FX `System.Messaging`, which is residing here: [Experimental.System.Messaging on GitHub](https://github.com/dotnetdev-kr/Experimental.System.Messaging).

This means that it might not work as expected. Or maybe it does? The tests seem to pass. All I'm saying is this: USE AT YOUR OWN RISK! 😨

Another difference is, that `MessageQueue.SetPermissions(...)` was not included in the port, so all automatically created queues will NOT have permissions set by default. This means that queues automatically created by code running under some systems account (as you normally would) will be owned and accessible only by that systems account. You need to have local administrator rights to fix this, and then go and take ownership of the queues, and THEN you may set the permissions... good times! 🙄