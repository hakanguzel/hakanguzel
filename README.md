```php
<?php

namespace HakanGuzel;

class About extends Me
{
    public function getCurrentWorkplace(): array
    {
        return [
            'workplace' => [
                'company' => 'Rise Technology, Consulting & Academy',
                'position' => 'Software Engineer'         
            ]
        ];
    }

    public function getDailyKnowledge(): array
    {
        return [
            NetCore::class,
            Php::class,
            NodeJS::class
        ];
    }

    public function getFutureGoal(): string
    {
        return 'To contribute to open source.';
    }
}
```
