# Making checklist for testing a Gmail

Suppose we'd want to test how sending emails via Google works ("Compose" feature). For this, we have to prepare a comprehensive list of checks,
that later will be used for actual manual testing. Writing a checklist helps overcome human memory imperfections. The more complex tested system is, the more necessary
becomes a mindmap of a system, which is the base of our future checklist. So the whole process consists of two components:

## Overview
1. Creating a mindmap
2. Writing a checklist based on mindmap

## 1. Creating a mindmap

Gmail's "Compose" greets us with a new window at the right bottom corner of a browser:

![Compose window](images/gmail_window.png)

We have to click through every clickable entity and register visually how system responds. There are text fields, menus, submenus, dropdowns, radiobuttons, etc. For future convinience, I also write these types alongside with names of functions. After this tedious procces the mind map is ready. You can see it below.

<img src="images/mindmap.png" width=800px>

## 2. Writing a checklist

Now we have to come up with a few checks for every branch of a mind map tree. This checks all should find system capable of performing tasks it was designed for
(positive check) and adequately respond to user's possible wrong actions at the same time (negative check). The checks are also have smoke, critical path, or extended
type, and I register that.

Let's start with control panel.
