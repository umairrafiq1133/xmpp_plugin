# xmpp_plugin

1. Connect to the xmpp server

```
final param = {
      "user_jid":"jid/resource",
      "password": "password",
      "host": "xmpphost",
      "port": "5222"
};

XmppConnection xmppConnection = XmppConnection(param);

await xmppConnection.start(_onReceiveMessage, _onError);
await xmppConnection.login();

```

2. Send message to one-one chat

```
await xmppConnection.sendMessageWithType("xyz@domain", "Hi", "MSGID");
await xmppConnection.sendGroupMessageWithType("xyz@conference.domain", "Hi", "MSGID");
```

3. Receive message from server

```
Future _onReceiveMessage(dynamic event) async {
       // TODO : Handle the receive event
}
```

4. Disconnect the xmppConnection

```
xmppConnection.logout();
```

5. Creating a MUC

```
xmppConnection.createMUC("groupName", true);
```

6. Joining  MUC

```
xmppConnection.joinMucGroups(List<String> allGroupsId)

```

7. Sending Custom Message

```
await xmppConnection.sendCustomMessage("xyz@domain", "Hi", "MSGID","customTest");
await xmppConnection.sendCustomGroupMessage("xyz@conference.domain", "Hi", "MSGID","customText");

```

8. Sending Delivery Receipt

```
await flutterXmpp.sendDelieveryReceipt("xyz@domain", "Received-Message-Id", "Receipt-Id");
```

9. Add members in group
```
await flutterXmpp.addMembersInGroup("groupName", List<String> allMembersId);
```

10. Add Admins in group
```
await flutterXmpp.addAdminsInGroup("groupName", List<String> allMembersId);
```

11. getMembers
```
await flutterXmpp.getMembers("groupName");
```

12. getAdmins
```
await flutterXmpp.getAdmins("groupName");
```

13. getOwners
```
await flutterXmpp.getOwners("groupName");
```

14. Remove members from group
```
await flutterXmpp.removeMember("groupName", List<String> allMembersId);
```

15. Remove admins from group
```
await flutterXmpp.removeAdmin("groupName", List<String> allMembersId);
```

16. get online member count from group
```
await flutterXmpp.getOnlineMemberCount("groupName");
```

17. get last seen
```
await flutterXmpp.getLastSeen(jid);
```

18. get my rosters
```
 await flutterXmpp.getMyRosters();
```

19. create roster
```
await flutterXmpp.createRoster(jid);
```



# To be Added

 - MAM
 - Presence
 - Last Activity
