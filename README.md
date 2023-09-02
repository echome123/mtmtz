# 美团每天赚

## 使用

```
<?php

declare(strict_types=1);
/**
 * This file is part of msmm.
 */

namespace App\Helper\Sdk;

use Msmm\MtMtz\Client;
use Msmm\MtMtz\Requests\ApiQueryOrderRequest;

class ToolMtMTZ
{
    /**
     * 获取订单.
     * @throws \Exception
     */
    public function pullOrder(): array {
        $client = new Client();
        $client->setAppKey('xxxx');
        $client->setSecret('xxxx');

        $request = new ApiQueryOrderRequest();
        $request->setStartTime(time() - 3600);
        $request->setEndTime(time());
        $request->setPage(1);
        $request->setLimit(20);
        $request->setQueryTimeType(1);
        $request->setBusinessLine([7]);

        return $client->execute($request);
    }
}
```
