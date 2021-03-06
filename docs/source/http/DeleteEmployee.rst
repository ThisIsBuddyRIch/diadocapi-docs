DeleteEmployee
==============

.. http:post:: /DeleteEmployee

    :query boxId: идентификатор ящика
    :query userId: идентификатор пользователя

    :reqheader Authorization: необходимые данные для :doc:`авторизации <../Authorization>`

    :statuscode 200: операция успешно завершена
    :statuscode 400: данные в запросе имеют неверный формат или отсутствуют обязательные параметры
    :statuscode 401: в запросе отсутствует HTTP-заголовок ``Authorization``, или в этом заголовке содержатся некорректные авторизационные данные
    :statuscode 402: закончилась подписка на API
    :statuscode 403: доступ к ящику с предоставленным авторизационным токеном запрещен или запрос сделан не от имени администратора
    :statuscode 404: сотрудник с переданными идентификаторами не найден
    :statuscode 405: используется неподходящий HTTP-метод
    :statuscode 500: при обработке запроса возникла непредвиденная ошибка

Удаляет сотрудника организации. Если сотрудник уже был удален, то действий не выполняется, а запрос завершается успешно.

Запрос доступен только администраторам организации.

Примеры использования (C#)
--------------------------

Пример удаления сотрудника c идентификатором пользователя userId из ящика с boxId:

.. code-block:: csharp

    api.DeleteEmployee(boxId, userId);