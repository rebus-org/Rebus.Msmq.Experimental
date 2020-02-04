# Rebus.Msmq.Experimental

[![install from nuget](https://img.shields.io/nuget/v/Rebus.Msmq.Experimental.svg?style=flat-square)](https://www.nuget.org/packages/Rebus.Msmq)

Provides a Microsoft Message Queue transport for [Rebus](https://github.com/rebus-org/Rebus).

![](https://raw.githubusercontent.com/rebus-org/Rebus/master/artwork/little_rebusbus2_copy-200x200.png)

---

NOTE THAT THIS PACKAGE IS BASED ON [Experimental.System.Messaging](https://www.nuget.org/packages/Experimental.System.Messaging/), which is NOT Microsoft's official MSMQ driver.

The reason for this package to exist, is because Microsoft chose to abandon the entire `System.Messaging` namespace when they ported code to .NET Core.

You can read more in [this GitHub issue: 'Add support for SystemMessaging and SOAP Web Services'](https://github.com/dotnet/runtime/issues/16409).