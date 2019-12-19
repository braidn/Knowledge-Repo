# Pheonix

[[toc]]

## Notes

## Getting Started

* The hex package manager:
  `mix local.hex`
* The phx.new mix command/cli tool:
  `mix archive.install hex phx_new {version}`

## Contexts

* [Elixir module that acts like a small boundary][edoc] around a given [resource][ecto]
* Often times resources are namespaced using a combination of module name + resource:
  * ex: `chat_conversations` for the Chat module and Conversation resource.
  * In the above case, 'chat_conversations' would be the db table name.

[edoc]: https://hexdocs.pm/phoenix/Mix.Tasks.Phx.Gen.Context.html
[ecto]: ./Ecto.md
