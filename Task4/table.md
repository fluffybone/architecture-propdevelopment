| Роль  | Права роли | Группы пользователей |
| --- | --- | --- |
| Название роли, которое отвечает требованиям RBAC в Kubernets. | Укажите права, которые необходимо выдать этой роли. | Выделите группы пользователей в организации, которые нужно связать с этой ролью. |
|Роль **cluster-pod-reader**  | нужны права на чтение информации (get,list,watch), resources: ["pods"]  |для DevOps-инженеров, для аналитиков, и например для привлеченных аудиторов |
|Роль **client-services-secrets-manager** в namespace **client-services** (Группа сервисов клиентов) |Права на чтение и изменение, resources: ["secrets"] (get,list,watch, create, update, patch)|для безопасников работающих с сервисом клиентов| 
|Роль **app-developer-role** для разработчиков в выделенном namespace  (например,team-frontend) |Права на чтение, изменения и удаления(get,list,watch, create, update,delete, patch) resources: ["pods"]|Backend Developers,Frontend Developers,Mobile Team— разработчики, отвечающие за свои сервисы|