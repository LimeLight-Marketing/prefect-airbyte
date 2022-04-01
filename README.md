# prefect-airbyte

## Welcome!

`prefect-airbyte` is a collections of prebuilt Prefect tasks that can be used to quickly construct Prefect flows.

## Getting Started

### Python setup

Requires an installation of Python 3.7+

We recommend using a Python virtual environment manager such as pipenv, conda or virtualenv.

These tasks are designed to work with Prefect 2.0. For more information about how to use Prefect, please refer to the [Prefect documentation](https://orion-docs.prefect.io/).

### Installation

Install `prefect-airbyte`

```bash
pip install prefect-airbyte
```

### Airbyte setup



### Write and run a flow

```python
from prefect import flow
from prefect.context import get_run_context
from prefect_airbyte import trigger_sync


@flow
def airbyte_connection() ->:
      pass
```

## Resources

If you encounter and bugs while using `prefect-airbyte`, feel free to open an issue in the [prefect-airbyte](https://github.com/PrefectHQ/prefect-airbyte) repository.

If you have any questions or issues while using `prefect-airbyte`, you can find help in either the [Prefect Discourse forum](https://discourse.prefect.io/) or the [Prefect Slack community](https://prefect.io/slack)

## Development

If you'd like to install a version of `prefect-airbyte` for development, first clone the repository and then perform an editable install with `pip`:

```bash
git clone https://github.com/PrefectHQ/prefect-airbyte.git

cd prefect-airbyte/

pip install -e ".[dev]"
```
