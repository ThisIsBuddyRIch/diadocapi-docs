RecycleDraft
============

Имя ресурса: **/RecycleDraft**

HTTP метод: **POST**

Параметры строки запроса:

-  *boxId* - идентификатор ящика;

-  *draftId* - идентификатор черновика.

В запросе должен присутствовать HTTP-заголовок ``Authorization`` с необходимыми данными для :doc:`авторизации <../Authorization>`.

Метод позволяет удалять еще не утилизированные черновики. Он может применяться к черновикам, которые не были преобразованы в полноценные сообщения и не были удалены ранее.

Возможные HTTP-коды возврата:

-  200 (OK) - операция успешно завершена;

-  400 (Bad Request) - данные в запросе имеют неверный формат или отсутствуют обязательные параметры;

-  401 (Unauthorized) - в запросе отсутствует HTTP-заголовок ``Authorization``, или в этом заголовке содержатся некорректные авторизационные данные;

-  403 (Forbidden) - доступ к ящику с предоставленным авторизационным токеном запрещен;

-  404 (Not found) - не найден черновик с заданным идентификатором;

-  405 (Method not allowed) - используется неподходящий HTTP-метод;

-  409 (Conflict) - попытка удаления уже утилизированного черновика;

-  500 (Internal server error) - при обработке запроса возникла непредвиденная ошибка.