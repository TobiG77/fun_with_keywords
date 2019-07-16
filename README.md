# FunWithKeywords

** Showcasing the pitfall of Keyword list merging in umbrella apps**

Consider a scenario where you have an umbrella app where multiple applications use the same driver and may want to set certain configuration options. Specifying the options in each app utilising the driver can easily lead to overwriting the option desired by another app.

To observe, simply run `iex -S mix` and inside the iex shell run:

```
Application.get_all_env(:alpha)

```

which will return:

[name: "GAMMA_DEV"]

since  apps/gamma/config/dev.exs overwrote the settings specified in apps/alpha/config/dev.exs and  apps/beta/config/dev.exs
