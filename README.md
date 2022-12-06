# Minimalistic Tor Controller

This is a mirror of the [main repository](https://declassed.art/repository/torcontrol).

Minimalistic asyncio-based Tor controller.

How to use:

```python

    from torcontrol import TorController

    async with TorController('127.0.0.1', 9051) as tc:
        await tc.authenticate('my-secret-password')
        async for circuit in tc.get_circuits():
            print(circuit)
```

This controller neither does nor will implement auto reconnect.
It's the user's responsibility to catch any exceptions
and re-run the entire `async with TorContrller...` code block.

All response parsing is very minimalistic. E.g. date/time strings are not parsed.

Currently this project is at alpha stage because only small
subset of commands is implemented for this particular project:
https://declassed.art/repository/dtcm2 ([github mirror](https://github.com/declassed-art/clabate)).
