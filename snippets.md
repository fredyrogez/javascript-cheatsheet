

### Fonction wait()
    function wait(ms)
    {
        const t1 = performance.now();
        let t2 = null;
        do {
            t2 = performance.now();
        }
        while(t2-t1 < ms);
    }
