# [Dělení na vlákna](index.md)
## [Základy dělení na spravovaná vlákna](managed-threading-basics.md)
### [Vlákna a dělení na vlákna](threads-and-threading.md)
### [Výjimky ve spravovaných vláknech](exceptions-in-managed-threads.md)
### [Synchronizace dat pro vícevláknové zpracování](synchronizing-data-for-multithreading.md)
### [Stavy spravovaných vláken](managed-thread-states.md)
### [Vlákna v popředí a v pozadí](foreground-and-background-threads.md)
### [Dělení na spravovaná a nespravovaná vlákna ve Windows](managed-and-unmanaged-threading-in-windows.md)
### [Thread.Suspend, uvolňování paměti a bezpečné body](thread-suspend-garbage-collection-and-safe-points.md)
### [Úložiště vláken Thread Local: statická pole a datové sloty ve vztahu k vláknům](thread-local-storage-thread-relative-static-fields-and-data-slots.md)
### [Zrušení ve spravovaných vláknech](cancellation-in-managed-threads.md)
#### [Postupy: Naslouchání požadavkům zrušení dotazováním](how-to-listen-for-cancellation-requests-by-polling.md)
#### [Postupy: Registrace zpětných volání pro požadavky zrušení](how-to-register-callbacks-for-cancellation-requests.md)
#### [Postupy: Naslouchání požadavkům zrušení, které mají obslužné rutiny čekání](how-to-listen-for-cancellation-requests-that-have-wait-handles.md)
#### [Postupy: Naslouchání více požadavkům zrušení](how-to-listen-for-multiple-cancellation-requests.md)
## [Použití vláken a dělení na vlákna](using-threads-and-threading.md)
### [Vytváření vláken a předávání dat při spuštění](creating-threads-and-passing-data-at-start-time.md)
### [Pozastavování a obnovování vláken](pausing-and-resuming-threads.md)
### [Zničení vláken](destroying-threads.md)
### [Plánování vláken](scheduling-threads.md)
### [Spolupráce při rušení vláken](canceling-threads-cooperatively.md)
## [Doporučené postupy dělení na spravovaná vlákna](managed-threading-best-practices.md)
## [Funkce a objekty dělení na vlákna](threading-objects-and-features.md)
### [Spravovaný fond vláken](the-managed-thread-pool.md)
### [Časovače](timers.md)
### [EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent](eventwaithandle-autoresetevent-countdownevent-manualresetevent.md)
#### [EventWaitHandle](eventwaithandle.md)
#### [AutoResetEvent](autoresetevent.md)
#### [ManualResetEvent a ManualResetEventSlim](manualresetevent-and-manualreseteventslim.md)
#### [CountdownEvent](countdownevent.md)
### [Mutex – třídy](mutexes.md)
### [Propojené operace](interlocked-operations.md)
### [Zámky modulů pro čtení a zápis](reader-writer-locks.md)
### [Semaphore a SemaphoreSlim](semaphore-and-semaphoreslim.md)
### [Přehled primitiv synchronizace](overview-of-synchronization-primitives.md)
### [Barrier](barrier.md)
#### [Postupy: Synchronizace souběžných operací pomocí třídy Barrier](how-to-synchronize-concurrent-operations-with-a-barrier.md)
### [SpinLock](spinlock.md)
#### [Postupy: Použití struktury SpinLock pro synchronizaci nízké úrovně](how-to-use-spinlock-for-low-level-synchronization.md)
#### [Postupy: Povolení režimu sledování vláken ve struktuře SpinLock](how-to-enable-thread-tracking-mode-in-spinlock.md)
### [SpinWait](spinwait.md)
#### [Postupy: Použití objektu SpinWait pro implementaci dvoufázové operace čekání](how-to-use-spinwait-to-implement-a-two-phase-wait-operation.md)