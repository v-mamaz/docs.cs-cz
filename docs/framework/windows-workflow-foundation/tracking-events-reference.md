---
title: "Sledovací odkaz události"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c1c1ee87-f80a-449b-acd0-50d81eef116e
caps.latest.revision: "23"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: d54c8bd4c6a73b9ff5b4066832b557041d7dec0d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="tracking-events-reference"></a>Sledovací odkaz události
Během provádění pracovní postup v [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] vyvolá sledování událostí při jejich přesunu různými fázemi v celé jeho životnosti. Hostitel může přihlásit k odběru těchto událostí a aktualizovat stav průběhu pracovního postupu během celé jeho životnosti. Sledování události vyvolané jsou popsané v této části.  
  
## <a name="event-reference"></a>Odkaz na události  
  
|ID události|Úroveň události|Zpráva události|Klíčová slova|  
|--------------|-----------------|-------------------|--------------|  
|[100 - WorkflowInstanceRecord](../../../docs/framework/windows-workflow-foundation/100-workflowinstancerecord.md)|Informace o|TrackRecord = WorkflowInstanceRecord, ID instance = %1, RecordNumber = %2, EventTime = %3, ActivityDefinitionId = %4, stav = %5, poznámky = %6, ProfileName = %7|EndToEndMonitoring, řešení potíží, HealthMonitoring, WFTracking|  
|[101 - WorkflowInstanceUnhandledExceptionRecord](../../../docs/framework/windows-workflow-foundation/101-workflowinstanceunhandledexceptionrecord.md)|Chyba|TrackRecord = WorkflowInstanceUnhandledExceptionRecord, ID instance = %1, RecordNumber = %2, EventTime = %3, ActivityDefinitionId = %4, název = %5, SourceId = %6, SourceInstanceId = %7, SourceTypeName = %8, výjimka = %9, poznámky = % 10, ProfileName = % 11|EndToEndMonitoring, řešení potíží, HealthMonitoring, WFTracking|  
|[102 - WorkflowInstanceAbortedRecord](../../../docs/framework/windows-workflow-foundation/102-workflowinstanceabortedrecord.md)|Upozornění|TrackRecord = WorkflowInstanceAbortedRecord, ID instance = %1, RecordNumber = %2, EventTime = %3, ActivityDefinitionId = %4, důvod = %5, poznámky = %6, ProfileName = %7|EndToEndMonitoring, řešení potíží, HealthMonitoring, WFTracking|  
|[103 - ActivityStateRecord](../../../docs/framework/windows-workflow-foundation/103-activitystaterecord.md)|Informace o|TrackRecord = ActivityStateRecord, ID instance = %1, RecordNumber = %2, EventTime = %3, stav = %4, název = %5, ID = %6, ActivityInstanceId = %7, ActivityTypeName = %8, argumenty = %9, proměnné = % 10, poznámky = % 11, ProfileName = % 12|EndToEndMonitoring, řešení potíží, HealthMonitoring, WFTracking|  
|[104 - ActivityScheduledRecord](../../../docs/framework/windows-workflow-foundation/104-activityscheduledrecord.md)|Informace o|TrackRecord = ActivityScheduledRecord, ID instance = %1, RecordNumber = %2, EventTime = %3, název = %4, ID = %5, ActivityInstanceId = %6, ActivityTypeName = %7, ChildActivityName = %8, ChildActivityId = %9, ChildActivityInstanceId = % 10, ChildActivityTypeName = % 11, poznámky = ProfileName 12, % = % 13|EndToEndMonitoring, řešení potíží, HealthMonitoring, WFTracking|  
|[105 - FaultPropagationRecord](../../../docs/framework/windows-workflow-foundation/105-faultpropagationrecord.md)|Upozornění|TrackRecord = FaultPropagationRecord, ID instance = %1, RecordNumber = %2, EventTime = %3, FaultSourceActivityName = %4, FaultSourceActivityId = %5, FaultSourceActivityInstanceId = %6, FaultSourceActivityTypeName = %7, FaultHandlerActivityName = %8 FaultHandlerActivityId = %9, FaultHandlerActivityInstanceId = % 10, FaultHandlerActivityTypeName = % 11, chyby = % 12, IsFaultSource = 13, poznámky % = % 14, ProfileName = % 15|EndToEndMonitoring, řešení potíží, HealthMonitoring, WFTracking|  
|[106 - CancelRequestRecord](../../../docs/framework/windows-workflow-foundation/106-cancelrequestrecord.md)|Informace o|TrackRecord = CancelRequestedRecord, ID instance = %1, RecordNumber = %2, EventTime = %3, název = %4, ID = %5, ActivityInstanceId = %6, ActivityTypeName = %7, ChildActivityName = %8, ChildActivityId = %9, ChildActivityInstanceId = % 10, ChildActivityTypeName = % 11, poznámky = ProfileName 12, % = % 13|EndToEndMonitoring, řešení potíží, HealthMonitoring, WFTracking|  
|[107 – BookmarkResumptionRecord](../../../docs/framework/windows-workflow-foundation/107-bookmarkresumptionrecord.md)|Informace o|TrackRecord = BookmarkResumptionRecord, ID instance = %1, RecordNumber = %2, EventTime = %3, název = %4, SubInstanceID = %5, hodnota vlastnosti OwnerActivityName = %6, OwnerActivityId = %7, OwnerActivityInstanceId = %8, OwnerActivityTypeName = %9, poznámky = % 10, ProfileName = % 11|EndToEndMonitoring, řešení potíží, HealthMonitoring, WFTracking|  
|[108 - CustomTrackingRecordInfo](../../../docs/framework/windows-workflow-foundation/108-customtrackingrecordinfo.md)|Informace o|TrackRecord = CustomTrackingRecord, ID instance = %1, RecordNumber = %2, EventTime = %3, název = %4, název aktivity ActivityName = %5, ID = %6, ActivityInstanceId = %7, ActivityTypeName = %8, Data = %9, poznámky = % 10, ProfileName = % 11|UserEvents, EndToEndMonitoring, řešení potíží, HealthMonitoring, WFTracking|  
|[110 - CustomTrackingRecordWarning](../../../docs/framework/windows-workflow-foundation/110-customtrackingrecordwarning.md)|Upozornění|TrackRecord = CustomTrackingRecord, ID instance = %1, RecordNumber = %2, EventTime = %3, název = %4, název aktivity ActivityName = %5, ID = %6, ActivityInstanceId = %7, ActivityTypeName = %8, Data = %9, poznámky = % 10, ProfileName = % 11|UserEvents, EndToEndMonitoring, řešení potíží, HealthMonitoring, WFTracking|  
|[111 - CustomTrackingRecordError](../../../docs/framework/windows-workflow-foundation/111-customtrackingrecorderror.md)|Chyba|TrackRecord = CustomTrackingRecord, ID instance = %1, RecordNumber = %2, EventTime = %3, název = %4, název aktivity ActivityName = %5, ID = %6, ActivityInstanceId = %7, ActivityTypeName = %8, Data = %9, poznámky = % 10, ProfileName = % 11|UserEvents, EndToEndMonitoring, řešení potíží, HealthMonitoring, WFTracking|  
|[112 - WorkflowInstanceSuspendedRecord](../../../docs/framework/windows-workflow-foundation/112-workflowinstancesuspendedrecord.md)|Informace o|TrackRecord = WorkflowInstanceSuspendedRecord, ID instance = %1, RecordNumber = %2, EventTime = %3, ActivityDefinitionId = %4, důvod = %5, poznámky = %6, ProfileName = %7|EndToEndMonitoring, řešení potíží, HealthMonitoring, WFTracking|  
|[113 - WorkflowInstanceTerminatedRecord](../../../docs/framework/windows-workflow-foundation/113-workflowinstanceterminatedrecord.md)|Chyba|TrackRecord = WorkflowInstanceTerminatedRecord, ID instance = %1, RecordNumber = %2, EventTime = %3, ActivityDefinitionId = %4, důvod = %5, poznámky = %6, ProfileName = %7|EndToEndMonitoring, řešení potíží, HealthMonitoring, WFTracking|  
|[114 - WorkflowInstanceRecordWithId](../../../docs/framework/windows-workflow-foundation/114-workflowinstancerecordwithid.md)|Informace o|TrackRecord = WorkflowInstanceRecord, ID instance = %1, RecordNumber = %2, EventTime = %3, ActivityDefinitionId = %4, stav = %5, poznámky = %6, ProfileName = %7, WorkflowDefinitionIdentity = %8|HealthMonitoring WFTracking|  
|[115 - WorkflowInstanceAbortedRecordWithId](../../../docs/framework/windows-workflow-foundation/115-workflowinstanceabortedrecordwithid.md)|Upozornění|TrackRecord = WorkflowInstanceAbortedRecord, ID instance = %1, RecordNumber = %2, EventTime = %3, ActivityDefinitionId = %4, důvod = %5, poznámky = %6, ProfileName = %7, WorkflowDefinitionIdentity = %8|HealthMonitoring WFTracking|  
|[116 - WorkflowInstanceSuspendedRecordWithId](../../../docs/framework/windows-workflow-foundation/116-workflowinstancesuspendedrecordwithid.md)|Informace o|TrackRecord = WorkflowInstanceSuspendedRecord, ID instance = %1, RecordNumber = %2, EventTime = %3, ActivityDefinitionId = %4, důvod = %5, poznámky = %6, ProfileName = %7, WorkflowDefinitionIdentity = %8|HealthMonitoring WFTracking|  
|[117 - WorkflowInstanceTerminatedRecordWithId](../../../docs/framework/windows-workflow-foundation/117-workflowinstanceterminatedrecordwithid.md)|Chyba|TrackRecord = WorkflowInstanceTerminatedRecord, ID instance = %1, RecordNumber = %2, EventTime = %3, ActivityDefinitionId = %4, důvod = %5, poznámky = %6, ProfileName = %7, WorkflowDefinitionIdentity = %8|HealthMonitoring WFTracking|  
|[118 - WorkflowInstanceUnhandledExceptionRecordWithId](../../../docs/framework/windows-workflow-foundation/118-workflowinstanceunhandledexceptionrecordwithid.md)|Chyba|TrackRecord = WorkflowInstanceUnhandledExceptionRecord, ID instance = %1, RecordNumber = %2, EventTime = %3, ActivityDefinitionId = %4, název = %5, SourceId = %6, SourceInstanceId = %7, SourceTypeName = %8, výjimka = %9, poznámky = % 10, ProfileName = % 11, WorkflowDefinitionIdentity = % 12|WFTracking HealthMonitoring, WFTrackingHealthMonitoring,|  
|[119 - WorkflowInstanceUpdatedRecord](../../../docs/framework/windows-workflow-foundation/119-workflowinstanceupdatedrecord.md)|Informace o|TrackRecord = WorkflowInstanceUpdatedRecord, ID instance = %1, RecordNumber = %2, EventTime = %3, ActivityDefinitionId = %4, stav = %5, OriginalDefinitionIdentity = %6, UpdatedDefinitionIdentity = %7, poznámky = %8, ProfileName = %9|HealthMonitoring WFTracking|  
|[225 - TraceCorrelationKeys](../../../docs/framework/windows-workflow-foundation/225-tracecorrelationkeys.md)|Informace o|Vypočítat korelace klíč '%1' v nadřazeném oboru: %3' pomocí hodnoty '%2'.|Řešení potíží s WFServices|  
|[440 - StartSignpostEvent1](../../../docs/framework/windows-workflow-foundation/440-startsignpostevent.md)|Informace o|Aktivita hranic.|Řešení potíží s WFServices|  
|[441 - StopSignpostEvent1](../../../docs/framework/windows-workflow-foundation/441-stopsignpostevent.md)|Informace o|Aktivita hranic.|Řešení potíží s WFServices|  
|[1001 - WorkflowApplicationCompleted](../../../docs/framework/windows-workflow-foundation/1001-workflowapplicationcompleted.md)|Informace o|Instance pracovního postupu Id: '%1' byla dokončena v uzavřeném stavu.|WFRuntime|  
|[1002 - WorkflowApplicationTerminated](../../../docs/framework/windows-workflow-foundation/1002-workflowapplicationterminated.md)|Informace o|WorkflowApplication Id: "%1" byl ukončen. Dokončil v chybném stavu s výjimkou.|WFRuntime|  
|[1003 - WorkflowInstanceCanceled](../../../docs/framework/windows-workflow-foundation/1003-workflowinstancecanceled.md)|Informace o|Id instance pracovního postupu: '%1' byla dokončena v stav zrušeno.|WFRuntime|  
|[1004 - WorkflowInstanceAborted](../../../docs/framework/windows-workflow-foundation/1004-workflowinstanceaborted.md)|Informace o|Instance pracovního postupu Id: '%1' byla přerušena, s výjimkou.|WFRuntime|  
|[1005 - WorkflowApplicationIdled](../../../docs/framework/windows-workflow-foundation/1005-workflowapplicationidled.md)|Informace o|WorkflowApplication Id: "%1" se nečinnosti.|WFRuntime|  
|[1006 - WorkflowApplicationUnhandledException](../../../docs/framework/windows-workflow-foundation/1006-workflowapplicationunhandledexception.md)|Chyba|Id instance pracovního postupu: '%1' došlo k neošetřené výjimce.  Výjimka pochází z aktivity %2, DisplayName: '%3'.  Se provedou následující akce: %4.|WFRuntime|  
|[1007 - WorkflowApplicationPersisted](../../../docs/framework/windows-workflow-foundation/1007-workflowapplicationpersisted.md)|Informace o|WorkflowApplication Id: '%1' byla zachována.|WFRuntime|  
|[1008 - WorkflowApplicationUnloaded](../../../docs/framework/windows-workflow-foundation/1008-workflowapplicationunloaded.md)|Informace o|Instance pracovního postupu Id: '%1' bylo uvolněno.|WFRuntime|  
|[1009 - ActivityScheduled](../../../docs/framework/windows-workflow-foundation/1009-activityscheduled.md)|Informace o|Nadřazená aktivita %1, DisplayName: %2, identifikátor InstanceId: '%3' naplánované podřízené aktivity "%4", DisplayName: '%5', identifikátor InstanceId: '%6'.|WFRuntime|  
|[1010 - ActivityCompleted](../../../docs/framework/windows-workflow-foundation/1010-activitycompleted.md)|Informace o|Nadřazená aktivita %1, DisplayName: %2, identifikátor InstanceId: '%3' naplánované podřízené aktivity "%4", DisplayName: '%5', identifikátor InstanceId: '%6'.|WFRuntime|  
|[1011 - ScheduleExecuteActivityWorkItem](../../../docs/framework/windows-workflow-foundation/1011-scheduleexecuteactivityworkitem.md)|Verbose|Bylo naplánováno ExecuteActivityWorkItem aktivity %1, DisplayName: %2, identifikátor InstanceId: '%3'.|WFRuntime|  
|[1012 - StartExecuteActivityWorkItem](../../../docs/framework/windows-workflow-foundation/1012-startexecuteactivityworkitem.md)|Verbose|Od spuštění ExecuteActivityWorkItem aktivity %1, DisplayName: %2, identifikátor InstanceId: '%3'.|WFRuntime|  
|[1013 - CompleteExecuteActivityWorkItem](../../../docs/framework/windows-workflow-foundation/1013-completeexecuteactivityworkitem.md)|Verbose|ExecuteActivityWorkItem dokončení aktivity %1, DisplayName: %2, identifikátor InstanceId: '%3'.|WFRuntime|  
|[1014 - ScheduleCompletionWorkItem](../../../docs/framework/windows-workflow-foundation/1014-schedulecompletionworkitem.md)|Verbose|Bylo naplánováno CompletionWorkItem pro nadřazené aktivity '%1', DisplayName: %2, identifikátor InstanceId: '%3'.  Dokončení aktivity %4, DisplayName: '%5', identifikátor InstanceId: '%6'.|WFRuntime|  
|[1015 - StartCompletionWorkItem](../../../docs/framework/windows-workflow-foundation/1015-startcompletionworkitem.md)|Verbose|Spuštění provádění CompletionWorkItem pro nadřazené aktivity '%1', DisplayName: %2, identifikátor InstanceId: '%3'. Dokončení aktivity %4, DisplayName: '%5', identifikátor InstanceId: '%6'.|WFRuntime|  
|[1016 - CompleteCompletionWorkItem](../../../docs/framework/windows-workflow-foundation/1016-completecompletionworkitem.md)|Verbose|Bylo dokončeno CompletionWorkItem pro nadřazené aktivity '%1', DisplayName: %2, identifikátor InstanceId: '%3'. Dokončení aktivity %4, DisplayName: '%5', identifikátor InstanceId: '%6'.|WFRuntime|  
|[1017 - ScheduleCancelActivityWorkItem](../../../docs/framework/windows-workflow-foundation/1017-schedulecancelactivityworkitem.md)|Verbose|Bylo naplánováno CancelActivityWorkItem aktivity %1, DisplayName: %2, identifikátor InstanceId: '%3'.|WFRuntime|  
|[1018 - StartCancelActivityWorkItem](../../../docs/framework/windows-workflow-foundation/1018-startcancelactivityworkitem.md)|Verbose|Spuštění provádění CancelActivityWorkItem aktivity %1, DisplayName: %2, identifikátor InstanceId: '%3'.|WFRuntime|  
|[1019 - CompleteCancelActivityWorkItem](../../../docs/framework/windows-workflow-foundation/1019-completecancelactivityworkitem.md)|Verbose|CancelActivityWorkItem dokončení aktivity %1, DisplayName: %2, identifikátor InstanceId: '%3'.|WFRuntime|  
|[1020 - CreateBookmark](../../../docs/framework/windows-workflow-foundation/1020-createbookmark.md)|Verbose|Záložku byl vytvořen pro aktivity %1, DisplayName: %2, identifikátor InstanceId: '%3'.  NázevZáložky: %4, BookmarkScope: %5.|WFRuntime|  
|[1021 - ScheduleBookmarkWorkItem](../../../docs/framework/windows-workflow-foundation/1021-schedulebookmarkworkitem.md)|Verbose|Bylo naplánováno BookmarkWorkItem aktivity %1, DisplayName: %2, identifikátor InstanceId: '%3'.  NázevZáložky: %4, BookmarkScope: %5.|WFRuntime|  
|[1022 - StartBookmarkWorkItem](../../../docs/framework/windows-workflow-foundation/1022-startbookmarkworkitem.md)|Verbose|Spuštění provádění BookmarkWorkItem aktivity %1, DisplayName: %2, identifikátor InstanceId: '%3'.  NázevZáložky: %4, BookmarkScope: %5.|WFRuntime|  
|[1023 - CompleteBookmarkWorkItem](../../../docs/framework/windows-workflow-foundation/1023-completebookmarkworkitem.md)|Verbose|BookmarkWorkItem dokončení aktivity %1, DisplayName: %2, identifikátor InstanceId: '%3'. NázevZáložky: %4, BookmarkScope: %5.|WFRuntime|  
|[1024 - CreateBookmarkScope](../../../docs/framework/windows-workflow-foundation/1024-createbookmarkscope.md)|Verbose|Byla vytvořena BookmarkScope: %1.|WFRuntime|  
|[1025 - BookmarkScopeInitialized](../../../docs/framework/windows-workflow-foundation/1025-bookmarkscopeinitialized.md)|Verbose|BookmarkScope, který měl TemporaryId: '%1' byl inicializován s Id: '%2'.|WFRuntime|  
|[1026 - ScheduleTransactionContextWorkItem](../../../docs/framework/windows-workflow-foundation/1026-scheduletransactioncontextworkitem.md)|Verbose|Bylo naplánováno TransactionContextWorkItem aktivity %1, DisplayName: %2, identifikátor InstanceId: '%3'.|WFRuntime|  
|[1027 - StartTransactionContextWorkItem](../../../docs/framework/windows-workflow-foundation/1027-starttransactioncontextworkitem.md)|Verbose|Spuštění provádění TransactionContextWorkItem aktivity %1, DisplayName: %2, identifikátor InstanceId: '%3'.|WFRuntime|  
|[1028 - CompleteTransactionContextWorkItem](../../../docs/framework/windows-workflow-foundation/1028-completetransactioncontextworkitem.md)|Verbose|TransactionContextWorkItem dokončení aktivity %1, DisplayName: %2, identifikátor InstanceId: '%3'.|WFRuntime|  
|[1029 - ScheduleFaultWorkItem](../../../docs/framework/windows-workflow-foundation/1029-schedulefaultworkitem.md)|Verbose|Bylo naplánováno FaultWorkItem aktivity %1, DisplayName: %2, identifikátor InstanceId: '%3'.  Výjimka byla rozšířena z aktivity %4, DisplayName: '%5', identifikátor InstanceId: '%6'.|WFRuntime|  
|[1030 - StartFaultWorkItem](../../../docs/framework/windows-workflow-foundation/1030-startfaultworkitem.md)|Verbose|Spuštění provádění FaultWorkItem aktivity %1, DisplayName: %2, identifikátor InstanceId: '%3'.  Výjimka byla rozšířena z aktivity %4, DisplayName: '%5', identifikátor InstanceId: '%6'.|WFRuntime|  
|[1031 - CompleteFaultWorkItem](../../../docs/framework/windows-workflow-foundation/1031-completefaultworkitem.md)|Verbose|FaultWorkItem dokončení aktivity %1, DisplayName: %2, identifikátor InstanceId: '%3'. Výjimka byla rozšířena z aktivity %4, DisplayName: '%5', identifikátor InstanceId: '%6'.|WFRuntime|  
|[1032 - ScheduleRuntimeWorkItem](../../../docs/framework/windows-workflow-foundation/1032-scheduleruntimeworkitem.md)|Verbose|Modul runtime pracovní položky bylo naplánováno aktivity %1, DisplayName: %2, identifikátor InstanceId: '%3'.|WFRuntime|  
|[1033 - StartRuntimeWorkItem](../../../docs/framework/windows-workflow-foundation/1033-startruntimeworkitem.md)|Verbose|Spouštění spuštění pracovní položky modulu runtime pro aktivitu %1, DisplayName: %2, identifikátor InstanceId: '%3'.|WFRuntime|  
|[1034 - CompleteRuntimeWorkItem](../../../docs/framework/windows-workflow-foundation/1034-completeruntimeworkitem.md)|Verbose|Pracovní položky modulu runtime dokončení aktivity %1, DisplayName: %2, identifikátor InstanceId: '%3'.|WFRuntime|  
|[1035 - RuntimeTransactionSet](../../../docs/framework/windows-workflow-foundation/1035-runtimetransactionset.md)|Verbose|Modul runtime transakce byla nastavena pomocí aktivity %1, DisplayName: %2, identifikátor InstanceId: '%3'.  Provádění izolované k aktivitě %4, DisplayName: '%5', identifikátor InstanceId: '%6'.|WFRuntime|  
|[1036 - RuntimeTransactionCompletionRequested](../../../docs/framework/windows-workflow-foundation/1036-runtimetransactioncompletionrequested.md)|Verbose|Aktivita "%1", DisplayName: %2, identifikátor InstanceId: '%3' má naplánované dokončení transakce modulu runtime.|WFRuntime|  
|[. 1037 - RuntimeTransactionComplete](../../../docs/framework/windows-workflow-foundation/1037-runtimetransactioncomplete.md)|Verbose|Modul runtime transakce byla dokončena se stavem '%1'.|WFRuntime|  
|[1038 - EnterNoPersistBlock](../../../docs/framework/windows-workflow-foundation/1038-enternopersistblock.md)|Verbose|Zadávat žádné zachovat blok.|WFRuntime|  
|[1039 - ExitNoPersistBlock](../../../docs/framework/windows-workflow-foundation/1039-exitnopersistblock.md)|Verbose|Operace bude ukončena bez zachovat blok.|WFRuntime|  
|[1040 - InArgumentBound](../../../docs/framework/windows-workflow-foundation/1040-inargumentbound.md)|Verbose|V argumentu '%1' na aktivitu %2, DisplayName: %3, identifikátor InstanceId: '%4' byla svázána s hodnotou: %5.|WFActivities|  
|[1041 - WorkflowApplicationPersistableIdle](../../../docs/framework/windows-workflow-foundation/1041-workflowapplicationpersistableidle.md)|Informace o|WorkflowApplication Id: '%1' je nečinnosti a trvalá.  Se provedou následující akce: %2.|WFRuntime|  
|[1101 - WorkflowActivityStart](../../../docs/framework/windows-workflow-foundation/1101-workflowactivitystart.md)|Informace o|Instance pracovního postupu Id: '%1' E2E aktivity|WFRuntime|  
|[1102 - WorkflowActivityStop](../../../docs/framework/windows-workflow-foundation/1102-workflowactivitystop.md)|Informace o|Instance pracovního postupu Id: '%1' E2E aktivity|WFRuntime|  
|[1103 - WorkflowActivitySuspend](../../../docs/framework/windows-workflow-foundation/1103-workflowactivitysuspend.md)|Informace o|Instance pracovního postupu Id: '%1' E2E aktivity|WFRuntime|  
|[1104 - WorkflowActivityResume](../../../docs/framework/windows-workflow-foundation/1104-workflowactivityresume.md)|Informace o|Instance pracovního postupu Id: '%1' E2E aktivity|WFRuntime|  
|[1124 - InvokeMethodIsStatic](../../../docs/framework/windows-workflow-foundation/1124-invokemethodisstatic.md)|Informace o|InvokeMethod '%1' - metoda je statická.|WFRuntime|  
|[1125 - InvokeMethodIsNotStatic](../../../docs/framework/windows-workflow-foundation/1125-invokemethodisnotstatic.md)|Informace o|InvokeMethod '%1' - metoda nejsou statické.|WFRuntime|  
|[1126 - InvokedMethodThrewException](../../../docs/framework/windows-workflow-foundation/1126-invokedmethodthrewexception.md)|Informace o|V metodě volá aktivita '%1' došlo k výjimce. %2|WFRuntime|  
|[1131 - InvokeMethodUseAsyncPattern](../../../docs/framework/windows-workflow-foundation/1131-invokemethoduseasyncpattern.md)|Informace o|InvokeMethod '%1' - metoda používá asynchronní vzor '%2' a '%3'.|WFRuntime|  
|[1132 - InvokeMethodDoesNotUseAsyncPattern](../../../docs/framework/windows-workflow-foundation/1132-invokemethoddoesnotuseasyncpattern.md)|Informace o|InvokeMethod '%1' - metoda nepoužívá asynchronní vzor.|WFRuntime|  
|[1140 - FlowchartStart](../../../docs/framework/windows-workflow-foundation/1140-flowchartstart.md)|Informace o|Bylo naplánováno vývojový diagram '%1' - Start.|WFActivities|  
|[1141 - FlowchartEmpty](../../../docs/framework/windows-workflow-foundation/1141-flowchartempty.md)|Upozornění|Vývojový diagram '%1' - byla spuštěna s žádné Nodes.An došlo k výjimce v metodě volá aktivita '%1'. %2|WFActivities|  
|[1143 - FlowchartNextNull](../../../docs/framework/windows-workflow-foundation/1143-flowchartnextnull.md)|Informace o|Vývojový diagram ' %1'/FlowStep - další uzel má hodnotu null. Vývojový diagram provádění se ukončí.|WFActivities|  
|[1146 - FlowchartSwitchCase](../../../docs/framework/windows-workflow-foundation/1146-flowchartswitchcase.md)|Informace o|Vývojový diagram ' nebyla vybrána %1'/FlowSwitch – případ '%2'.|WFActivities|  
|[1147 - FlowchartSwitchDefault](../../../docs/framework/windows-workflow-foundation/1147-flowchartswitchdefault.md)|Informace o|Vývojový diagram ' nebyla vybrána %1'/FlowSwitch - výchozí případu.|WFActivities|  
|[1148 - FlowchartSwitchCaseNotFound](../../../docs/framework/windows-workflow-foundation/1148-flowchartswitchcasenotfound.md)|Informace o|Vývojový diagram ' %1'/FlowSwitch - může najít aktivitu případu ani výchozí případu odpovídající výsledek výrazu. Vývojový diagram provádění se ukončí.|WFActivities|  
|[1150 - CompensationState](../../../docs/framework/windows-workflow-foundation/1150-compensationstate.md)|Informace o|CompensableActivity '%1' je ve stavu '%2'.|WFActivities|  
|[1223 - SwitchCaseNotFound](../../../docs/framework/windows-workflow-foundation/1223-switchcasenotfound.md)|Informace o|Aktivita přepínači '%1' nelze nalézt aktivitu případu odpovídající výsledek výrazu.|WFActivities|  
|[1449 - WfMessageReceived](../../../docs/framework/windows-workflow-foundation/1449-wfmessagereceived.md)|Informace o|V pracovním postupu byla přijata zpráva|WFServices|  
|[1 450 - WfMessageSent](../../../docs/framework/windows-workflow-foundation/1450-wfmessagesent.md)|Informace o|Zpráva byla odeslána z pracovního postupu|WFServices|  
|[2021 - ExecuteWorkItemStart](../../../docs/framework/windows-workflow-foundation/2021-executeworkitemstart.md)|Verbose|Provedení spuštění pracovní položky|WFRuntime|  
|[2022 - ExecuteWorkItemStop](../../../docs/framework/windows-workflow-foundation/2022-executeworkitemstop.md)|Verbose|Spustit pracovní položku zastavení|WFRuntime|  
|[2023 - SendMessageChannelCacheMiss](../../../docs/framework/windows-workflow-foundation/2023-sendmessagechannelcachemiss.md)|Verbose|Neúspěšný přístup do SendMessageChannelCache|WFRuntime|  
|[2024 - InternalCacheMetadataStart](../../../docs/framework/windows-workflow-foundation/2024-internalcachemetadatastart.md)|Verbose|InternalCacheMetadata bylo zahájeno aktivity '%1'.|WFRuntime|  
|[2025 - InternalCacheMetadataStop](../../../docs/framework/windows-workflow-foundation/2025-internalcachemetadatastop.md)|Verbose|InternalCacheMetadata zastavily aktivity '%1'.|WFRuntime|  
|[2026 - CompileVbExpressionStart](../../../docs/framework/windows-workflow-foundation/2026-compilevbexpressionstart.md)|Verbose|Kompilování VB výrazu '%1.|WFRuntime|  
|[2027 - CacheRootMetadataStart](../../../docs/framework/windows-workflow-foundation/2027-cacherootmetadatastart.md)|Verbose|CacheRootMetadata aktivity "%1" bylo zahájeno|WFRuntime|  
|[2028 - CacheRootMetadataStop](../../../docs/framework/windows-workflow-foundation/2028-cacherootmetadatastop.md)|Verbose|CacheRootMetadata zastavily aktivity %1.|WFRuntime|  
|[2029 - CompileVbExpressionStop](../../../docs/framework/windows-workflow-foundation/2029-compilevbexpressionstop.md)|Verbose|Dokončení kompilování výrazů jazyka Visual Basic.|WFRuntime|  
|[2576 - TryCatchExceptionFromTry](../../../docs/framework/windows-workflow-foundation/2576-trycatchexceptionfromtry.md)|Informace o|Aktivita TryCatch '%1' má zjistilo výjimku typu '%2'.|WFActivities|  
|[2577 - TryCatchExceptionDuringCancelation](../../../docs/framework/windows-workflow-foundation/2577-trycatchexceptionduringcancelation.md)|Upozornění|Aktivita podřízené aktivity TryCatch '%1' došlo k výjimce při zrušení.|WFActivities|  
|[2578 - TryCatchExceptionFromCatchOrFinally](../../../docs/framework/windows-workflow-foundation/2578-trycatchexceptionfromcatchorfinally.md)|Upozornění|Catch nebo nakonec aktivity, která souvisí s aktivitou TryCatch '%1' došlo k výjimce.|WFActivities|  
|[3501 - InferredContractDescription](../../../docs/framework/windows-workflow-foundation/3501-inferredcontractdescription.md)|Informace o|ContractDescription s názvem = '%1' a Namespace = '%2' byla vyvozena z WorkflowService.|WFServices|  
|[3502 - InferredOperationDescription](../../../docs/framework/windows-workflow-foundation/3502-inferredoperationdescription.md)|Informace o|OperationDescription s názvem = '%1' ve smlouvě se z WorkflowService odvodit '%2'. IsOneWay = %3.|WFServices|  
|[3503 - DuplicateCorrelationQuery](../../../docs/framework/windows-workflow-foundation/3503-duplicatecorrelationquery.md)|Upozornění|Místo, kde byla nalezena duplicitní CorrelationQuery = '%1'. Tento dotaz duplicitní nebude používat při výpočtu korelace.|WFServices|  
|[3507 - ServiceEndpointAdded](../../../docs/framework/windows-workflow-foundation/3507-serviceendpointadded.md)|Informace o|Koncový bod služby byla přidána ke adresu '%1', vazby: %2' a kontrakt '%3'.|WFServices|  
|[3508 - TrackingProfileNotFound](../../../docs/framework/windows-workflow-foundation/3508-trackingprofilenotfound.md)|Verbose|'%1' TrackingProfile ActivityDefinitionId '%2' nebyla nalezena. Buď TrackingProfile nebyl nalezen v konfiguračním souboru nebo ActivityDefinitionId neodpovídá.|WFServices|  
|[3550 - BufferOutOfOrderMessageNoInstance](../../../docs/framework/windows-workflow-foundation/3550-bufferoutofordermessagenoinstance.md)|Informace o|Operaci '%1' nelze v tuto chvíli provést. Další pokus bude provádět, pokud je připraven ke zpracování této konkrétní operace v instanci služby.|WFServices|  
|[3551 - BufferOutOfOrderMessageNoBookmark](../../../docs/framework/windows-workflow-foundation/3551-bufferoutofordermessagenobookmark.md)|Informace o|Operace: %2' na instanci služby '%1' nelze v tuto chvíli provést. Další pokus bude provádět, pokud je připraven ke zpracování této konkrétní operace v instanci služby.|WFServices|  
|[3552 - MaxPendingMessagesPerChannelExceeded](../../../docs/framework/windows-workflow-foundation/3552-maxpendingmessagesperchannelexceeded.md)|Upozornění|Omezení limit 'MaxPendingMessagesPerChannel' % 1, který byl vybrán. Chcete-li tento limit zvýšit, upravte vlastnost MaxPendingMessagesPerChannel na BufferedReceiveServiceBehavior.|Kvóta WFServices|  
|[3557 - TransactedReceiveScopeEndCommitFailed](../../../docs/framework/windows-workflow-foundation/3557-transactedreceivescopeendcommitfailed.md)|Informace o|Volání EndCommit na CommittableTransaction s id = "%1" způsobila TransactionException – s následující zprávou: '%2'.|WFServices|  
|[4201 - EndSqlCommandExecute](../../../docs/framework/windows-workflow-foundation/4201-endsqlcommandexecute.md)|Verbose|Ukončení provedení příkazu SQL: %1|WFInstanceStore|  
|[4202 - StartSqlCommandExecute](../../../docs/framework/windows-workflow-foundation/4202-startsqlcommandexecute.md)|Verbose|Spouštění provedení příkazu SQL: %1|WFInstanceStore|  
|[4203 - RenewLockSystemError](../../../docs/framework/windows-workflow-foundation/4203-renewlocksystemerror.md)|Chyba|Prodloužit platnost uzamčení se nezdařilo, vypršení platnosti zámku již předán nebo vlastníka zámku byla odstraněna. Probíhá rušení SqlWorkflowInstanceStore.|WFInstanceStore|  
|[4205 - FoundProcessingError](../../../docs/framework/windows-workflow-foundation/4205-foundprocessingerror.md)|Chyba|Příkaz se nezdařil: %1|WFInstanceStore|  
|[4206 - UnlockInstanceException](../../../docs/framework/windows-workflow-foundation/4206-unlockinstanceexception.md)|Chyba|Došlo k výjimce %1 při pokusu o odemknutí instance.|WFInstanceStore|  
|[4207 - MaximumRetriesExceededForSqlCommand](../../../docs/framework/windows-workflow-foundation/4207-maximumretriesexceededforsqlcommand.md)|Informace o|Byly provedeny zkoušet opakováním příkazu SQL jako maximální počet opakovaných pokusů.|Kvóta WFInstanceStore|  
|[4208 - RetryingSqlCommandDueToSqlError](../../../docs/framework/windows-workflow-foundation/4208-retryingsqlcommandduetosqlerror.md)|Informace o|Opakováním příkazu SQL z důvodu SQL číslo chyby %1.|WFInstanceStore|  
|[4209 - TimeoutOpeningSqlConnection](../../../docs/framework/windows-workflow-foundation/4209-timeoutopeningsqlconnection.md)|Chyba|Časový limit pokusu o otevření připojení SQL. Operace nebyla dokončena v přiděleném časovém limitu % 1. Čas přidělený tato operace mohla být část delší časový limit.|WFInstanceStore|  
|[4210 - SqlExceptionCaught](../../../docs/framework/windows-workflow-foundation/4210-sqlexceptioncaught.md)|Upozornění|Zachycení zpráva o výjimce SQL číslo %1 %2.|WFInstanceStore|  
|[4211 - QueuingSqlRetry](../../../docs/framework/windows-workflow-foundation/4211-queuingsqlretry.md)|Upozornění|Řízení front opakování SQL s zpoždění %1 milisekundách.|WFInstanceStore|  
|[4212 - LockRetryTimeout](../../../docs/framework/windows-workflow-foundation/4212-lockretrytimeout.md)|Upozornění|Časový limit pokusu o získání zámku instance.  Operace nebyla dokončena v přiděleném časovém limitu % 1. Čas přidělený tato operace mohla být část delší časový limit.|WFInstanceStore|  
|[4213 - RunnableInstancesDetectionError](../../../docs/framework/windows-workflow-foundation/4213-runnableinstancesdetectionerror.md)|Chyba|Detekování spustitelného instance se nezdařilo kvůli následující výjimce|WFInstanceStore|  
|[4214 - InstanceLocksRecoveryError](../../../docs/framework/windows-workflow-foundation/4214-instancelocksrecoveryerror.md)|Chyba|Obnovení zámky instance se nezdařilo z důvodu následující výjimky|WFInstanceStore|  
|[39456 - TrackingRecordDropped](../../../docs/framework/windows-workflow-foundation/39456-trackingrecorddropped.md)|Upozornění|Velikost sledování záznam %1 překračuje maximální povolenou relace trasování událostí pro Windows pro zprostředkovatele: %2|WFTracking|  
|[39457 - TrackingRecordRaised](../../../docs/framework/windows-workflow-foundation/39457-trackingrecordraised.md)|Informace o|Sledování záznam %1 na %2.|WFRuntime|  
|[39458 - TrackingRecordTruncated](../../../docs/framework/windows-workflow-foundation/39458-trackingrecordtruncated.md)|Upozornění|Zkrácená sledování záznam %1 zapsána do relace trasování událostí pro Windows pomocí zprostředkovatele %2. Odebrali jsme proměnné a poznámky nebo uživatelská data|WFTracking|  
|[39459 - TrackingDataExtracted](../../../docs/framework/windows-workflow-foundation/39459-trackingdataextracted.md)|Verbose|Sledování dat %1 extrahovat aktivity %2.|WFRuntime|  
|[39460 - TrackingValueNotSerializable](../../../docs/framework/windows-workflow-foundation/39460-trackingvaluenotserializable.md)|Upozornění|Extrahované argument nebo proměnná '%1' není serializovatelný.|WFTracking|  
|[57398 - MaxInstancesExceeded](../../../docs/framework/windows-workflow-foundation/57398-maxinstancesexceeded.md)|Upozornění|Systém dosáhl limit nastavený pro omezení 'MaxConcurrentInstances'. Limit pro toto omezení byla nastavena na %1. Hodnota omezení lze změnit úpravou atribut 'maxConcurrentInstances' v omezení ServiceThrottle s hodnotou elementu nebo úpravou vlastnosti 'MaxConcurrentInstances' na chování třídy ServiceThrottlingBehavior.|WFServices|