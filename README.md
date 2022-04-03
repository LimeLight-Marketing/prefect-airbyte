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
See [the airbyte documention]() on how to get your own instance.


### Examples

#### Trigger a defined connection sync
```python
from prefect import flow
from prefect_airbyte.connections import trigger_sync


@flow
def example_trigger_sync_flow():

      # Run other tasks and subflows here

      trigger_sync(
            connection_id="your-connection-id-to-sync"
      )

example_trigger_sync_flow()
```

#### Export an Airbyte instance's configuration
```python
import gzip

from prefect import flow, task
from prefect_airbyte.configuration import export_configuration

@task
def zip_and_write_somewhere(
      airbyte_config: bytearray
      somwhere: str = 'my_destination.gz','
):
      with gzip.open('my_destination.gz', 'wb') as f:
            f.write(airbyte_configuration)

@flow
def example_export_configuration_flow():

      # Run other tasks and subflows here

      airbyte_config = export_configuration(
            airbyte_server_host="localhost",
            airbyte_server_port="8000",
            airbyte_api_version="v1",
      )

      zip_and_write_somewhere(airbyte_config=airbyte_config)

example_trigger_sync_flow()
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
