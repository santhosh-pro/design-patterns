//https://www.typescriptlang.org/play?#code/FAYwNghgzlAEBqBTEALAlmRBhA9gOwBdEAPA2Ab2GFhtgAcAnNANwiNigIbcQHMBPAFwJk6TAGUuPAQG4qtWCHycGAVxAEcDABQrpQkagyJJ3IgICUFagtoF0UAHR7z-WAF4OU13IUBfeVo6VQAjMDQQDkQCU31dbz4DJCMJBMtrWzsHZzS3TxdE31oAmxpgsIivCAYCbQthZhw0ABMMzNh7NCcCgRzq2os5UtgAkrRCRAYAMwgQREMxE1y2mk5+uoam5rkS8Gg4LGrYNABbOkwTxEI4ZMXY1xX6UPDItZq6x4UlPCgcTEcwDheNoAOSHBiwST9EGDYajKh7GCwABCqjgp3OiEu1wWxnuiUe5ReVXeVko7UUyj+iABQNBqLgUJqMKKNHhwAA9BzQMoyN8iKQPLA8IgAO64zC4CakbQi8UMuqw-kkAh9UlyZWkZzRfECWVi2DgxUa-AC1VvAZDIA

class VechileContext {

    private strategy: VechileStrategy;

    constructor(strategy: VechileStrategy) {
        this.strategy = strategy;
    }

    public setStrategy(strategy: VechileStrategy) {
        this.strategy = strategy;
    }

    public start(): void {
        this.strategy.start();

    }
}

interface VechileStrategy {
    start(): void;
}

class Car implements VechileStrategy {
    public start() {
        console.log('Car Start');
    }
}

class Bus implements VechileStrategy {
    public start() {
        console.log('Bus Start');
    }
}

//
const context = new VechileContext(new Bus());
context.start();
context.setStrategy(new Car());
context.start();
