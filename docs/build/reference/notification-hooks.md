---
title: "通知フック |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- delayed loading of DLLs, notification hooks
ms.assetid: e9c291ed-2f2d-4319-a171-09800625256f
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 31490e3bb591af6568ffecddf68219c89a25e055
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="notification-hooks"></a>通知フック
通知フックはヘルパー ルーチンで、次の操作が実行される直前に呼び出されます。  
  
-   ライブラリに格納されたハンドルはかどうか、既に読み込まれているを確認しました。  
  
-   **LoadLibrary** DLL の読み込みを試行すると呼びます。  
  
-   **GetProcAddress**プロシージャのアドレスを取得しようとすると呼びます。  
  
-   遅延インポートの戻り値は、サンクを読み込みます。  
  
 通知フックが有効です。  
  
-   ポインターの新しい定義を指定することによって**__pfnDliNotifyHook2**指すように、通知を受け取る関数に初期化します。  
  
     - または -  
  
-   マウス ポインターを設定して**__pfnDliNotifyHook2**プログラムは、DLL への呼び出しの遅延読み込みする前に、フック関数をします。  
  
 場合は、通知は**dliStartProcessing**、フック関数が返すことができます。  
  
 NULL  
 既定のヘルパーは、DLL の読み込みを処理します。 これは情報提供を目的に対してのみ呼び出すことに役立ちます。  
  
 関数ポインター  
 既定の遅延読み込みの処理をバイパスします。 これにより、独自のロード ハンドラーを指定できます。  
  
 場合は、通知は**dliNotePreLoadLibrary**、フック関数が返すことができます。  
  
-   情報を通知だけ必要がある場合は 0。  
  
-   DLL 自体が読み込まれている場合は、読み込まれた DLL の HMODULE です。  
  
 場合は、通知は**dliNotePreGetProcAddress**、フック関数が返すことができます。  
  
-   情報を通知だけ必要がある場合は 0。  
  
-   フック関数は、アドレス自体を取得する場合は、インポートされた関数のアドレス。  
  
 場合は、通知は**dliNoteEndProcessing**、フック関数の戻り値は無視されます。  
  
 このポインターは、(0 以外) は初期化、遅延読み込みヘルパーは、実行中の通知の特定の時点での関数を呼び出します。 関数ポインターには、次の定義があります。  
  
```  
// The "notify hook" gets called for every call to the  
// delay load helper.  This allows a user to hook every call and  
// skip the delay load helper entirely.  
//  
// dliNotify == {  
//  dliStartProcessing |  
//  dliNotePreLoadLibrary  |  
//  dliNotePreGetProc |  
//  dliNoteEndProcessing}  
//  on this call.  
//  
ExternC  
PfnDliHook   __pfnDliNotifyHook2;  
  
// This is the failure hook, dliNotify = {dliFailLoadLib|dliFailGetProc}  
ExternC  
PfnDliHook   __pfnDliFailureHook2;  
```  
  
 通知を渡す、 **DelayLoadInfo**通知値と一緒にフック関数を構造体。 このデータは、遅延読み込みヘルパー ルーチンが使用するものと同じです。 通知の値で定義されている値のいずれかになります[構造体と定数定義](../../build/reference/structure-and-constant-definitions.md)です。  
  
## <a name="see-also"></a>参照  
 [エラー処理と通知](../../build/reference/error-handling-and-notification.md)