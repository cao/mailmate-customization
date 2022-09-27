# MailMate Customization

I regularly use [MailMate](https://manual.mailmate-app.com/) as my email client because it allows customization.

To make it more to my liking, I have:

1. Added a set of custom key bindings that are inspired by Vi/Mutt/Gmail.
2. Added a custom fixed layout view that ports the correspondence view to widescreen.
3. Freed normal key bindings via "System Preferences -> Keyboard -> Shortcuts -> App Shortcuts".

## Key Bindings

    # Viewing/Reading Messages
    # If the message pane is focused, then the key bindings affect the messages pane
    # If the message pane is not focused, then the key bindings affect the correspondence pane
    j/k             Select next/previous message
    J/K             Select current email and move down/up (always in messages pane!)
    n/p             Go to next/previous thread
    h/l             Collapse/expand thread
    S-Space/Space   Scroll up/down in content pane
    P/:             Scroll up/down in content pane
    u               Toggle read/unread status
    s               Toggle starred status
    e               Archive
    v               Move message (opens move message window)
    !               Move to junk
    #               Delete message (also bound to Command-Backspace)
    c               New message
    r               Reply all
    R               Reply reply-to (sender) only
    f               Forward message
    O               Show previous format (usually used to go back to plaintext)
    o               Show next format (usually to go to HTML)
    L               Load images once
    d               Save attachments
    T               Show/focus thread (leave view with Backspace/Esc)

    # Composing
    Command-I       Focus identity selector ("From")
    Command-S       Focus signature selector
    Command-M       Toggle markdown mode
    Command-K       Toggle markdown preview (when in compose mode)

    # General
    /               Search all messages
    z               Undo
    Z               Redo
    Backspace       Go back in history
    Shift-Backspace Go forward in history

    # Movement
    ;               Go to inbox (opens go to mailbox window)
    Command-J/K     Go to next/previous inbox (pane does not to be focused)
    Option-J/K      Go to next/previous inbox with non-zero count (pane does not to be focused)
    gg              Go to first message in messages/correspondence pane (depending on focus)
    gi              Go to inbox mailbox
    gd              Go to drafts mailbox
    gs              Go to starred/flagged messages mailbox
    gt              Go to sent messages mailbox
    G               Go to last message in messages/correspondence pane (depending on focus)

    # Focusing
    Command-h       Focus mailbox pane
    Command-j/8     Focus correspondence pane
    Command-k/9     Focus messages pane
    Command-l/0     Focus message view (useful scrolling)

## Installation

To install the custom key bindings and/or custom layout, you just need to symlink them:

    mkdir -p "~/Library/Application Support/MailMate/Resources/KeyBindings"
    ln -s KeyBindings/cao.plist "~/Library/Application Support/MailMate/Resources/KeyBindings/cao.plist"

    mkdir -p "~/Library/Application Support/MailMate/Resources/Layouts/Mailboxes"
    ln -s Layouts/Mailboxes/wide_correspondence.plist "~/Library/Application Support/MailMate/Resources/Layouts/Mailboxes/wide_correspondence.plist"

## Remapping of Conflicting Key Bindings

The following MailMate key bindings conflicted for me, and I remapped them to Shift-Control-Option-Command-F12, as unmapping seems to be impossible:

- Move to Junk
- Jump to Selection
- Delete
- Delete Now
- Hide MailMate

# Known Issues

There are some issues that I have not been able to look into.
If you know how to resolve them, I would appreciate if you would let me know.

1. When deleting an email, multiple messages might become selected (via the correspondence pane).
2. Panes might not get restored to original size (this might be an interaction with automatic resizing via Yabai). It might make sense to just fix them to a specific size.
