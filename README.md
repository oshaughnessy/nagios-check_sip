nagios-check_sip
================

Nagios plugin to check the responsiveness of a SIP server


## Usage

    check_sip [<flags>] -H host [-c contact_uri] [-P proxy] [-p port] [-u user] [-a pass] [-e exp] [-v]
    check_sip [<flags>] -U sip_uri [-c contact_uri] [-P proxy] [-a pass] [-e exp] [-v]
    check_sip --help
    check_sip --man
    check_sip --version

    Options:
      --contact|c   Contact URI to use in register (def <given user>@this_host).
      --expires|e   Set an expiration time for registrations (def 300).
      --hostname|H  Name of the host running the SIP server.
      --password|a  Auth password to specify when sending a username.
      --port|p      Port on which the SIP service should be running (def 5060).
      --proxy|P     Outbound proxy hostname; use if different than SIP URI host.
      --user|u      Username to include in the SIP uri.
      --uri|U       Full sip:user@host[:port] URI.
      --verbose|-v  Show details of progress (give more than once for more info).
      --help        Show this usage text.
      --man         Show the comprehensive documentation.
      --version     Show the version (0.1.6).

      Normal behavior is to send an OPTIONS request to the SIP server.
      If a username is given, though, either through --user or --uri, the
      script will attempt to register with the server given in the SIP URI.


## Requirements

This script uses [sipsak](http://www.sipsak.org).


## To Do

Move from utils.pm to Nagios::Plugin.  Patches welcome :-)


## License

This code is licensed under the Perl Artistic License, version 2.0.  For
more information, please see the file Artistic_2.0, which was included with
this distribution, or http://opensource.org/licenses/artistic-license-2.0.php
