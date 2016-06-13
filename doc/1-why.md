# Why Another Framework?

Despite their proliferation, the design of web-frameworks is hardly settled. This is due to the increasing range of functions expected from a framework. In the simplest case a framework may host the implementation of a web app. However web APIs are increasingly common. Additionally, the increasing use of web-sockets places more demands on frameworks.

## The Status Quo

A common approach is to extend an existing framework to support these new features. In some cases, this has worked well. Web APIs have a very similar set of requirements to browsers — this is intentional in their design. In other case I believe things are more awkward. Consider web-sockets. In a classic MVC framework, communication over web-sockets is a poor fit. A persistent connection doesn't map well to the URL-centric request/response cycle of MVC.

## Intertwined Concepts

## Duplication

## Separate and Order
