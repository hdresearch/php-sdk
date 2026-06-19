# Orchestrator Control Plane API PHP SDK

> vers-sdk v1.20.0

It is generated with [Sterling](https://github.com/hdresearch/sterling).

## Requirements

- PHP >= 8.1
- ext-curl
- ext-json

## Installation

```bash
composer require vers/sdk
```

## Usage

```php
<?php

require_once 'vendor/autoload.php';

use VersSdk\VersSdkClient;

$client = new VersSdkClient(
    apiKey: 'your-api-key',
);

// Example: call an API operation
// $result = $client->operationName();
```

## Configuration

| Option       | Description                | Default                          |
|-------------|----------------------------|----------------------------------|
| `baseUrl`   | API base URL               | `https://api.vers.sh`                   |
| `apiKey`    | Bearer token for auth      | `VERS_API_KEY` env var           |
| `maxRetries`| Maximum retry attempts     | `2`                              |
| `timeout`   | Request timeout (seconds)  | `30.0`                           |

## Error Handling

```php
use VersSdk\ApiException;
use VersSdk\NotFoundException;

try {
    $result = $client->someOperation();
} catch (NotFoundException $e) {
    echo "Not found: " . $e->getMessage();
} catch (ApiException $e) {
    echo "API error ({$e->status}): " . $e->getMessage();
}
```

## License

MIT
