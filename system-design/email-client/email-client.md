# Email Client

- design a desktop email client like Microsoft Outlook and Apple Mail

# Requirements

Function requirements

- Have a client that
  - shows list of emails to the left
  - shows emails of read or not
  - when clicking on list ...show the email details to the right
  - Have inbox
  - have Drafts
  - have junk
  - trash
  - have cateogries

Non-functional requirements

- have an email server to store emails
- have drafts to user's storage
- have some sort of polling of X minutes to get new emails

# Architecture

- use excalidraw

# Data Models

... in png

# Interface (API)

... in png

# Optimizations

... in png

--

## Requirements

- Sending email messages SMTP server
- retrieving emails from imap server
- access emails on device
- OS? windows, mac, linux?
- whichs accounts need to be supported? assume user can make authed requiests to smtp and imap servers
- work offline? users should able to browse and search...outgoing messages should be saved..sent when it comes back online
- email threading?

## Background Knowledge

- SMTP and IMAP protocols.... treat it like HTTP
- Email systems
  - Mail user Agent MUA - app where users can compose , send , receive, and read email messages..
    other non-core functionalities..... searching, flagging, address books
  - Mail Transfer Agent (MTA) - software that transfers email messages from one host to another
  - Mail servers - computers which host MTAs the email messages in mailbox
  - Mailbox: concept that contails messages and exist on mail servers

Mail transport Protocols

- SMTP is outgoing mail
- POP and IMAP is incoming mail

Simple Mail Transport Protocol (SMTP)

- sends emails
- transfer messages, authenticates, specify recipients, and sending the message

Post Office Protocol (POP)

- post office .. email is there..until it is downloaded

Internet messaage Access Protcol (IMAP)

- IMAP allows userse to retrieve and manage email messages within webmail and email clients...
  w/o downloading them to local computer....

POP is outdated vs IMAP.

FLOW

- Sender: webmail goes to web app server ...then to email service...where as email client can directly go to mail service
- Receiver: Outlook server polls to email client... via IMAP, for webmail ... it polls from mail seriver..then reaches back webmail

## Types of Email System

- Store and Forward servers (POP)
- Server-only mailboxes
- Server mailbox with client-side cache

## Architecture / high-level design

- Flux architecture
- Commany query request separation
- central store..same data store
- namespaced commands for better organization...lower chance of collision
- CSR because it's an app
- Task queue

Command Query Separation
query: returns a result that doesn't modify state
commands: modifies state but doesn't return a value
