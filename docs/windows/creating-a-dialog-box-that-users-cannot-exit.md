---
title: "ユーザーが終了できないダイアログ ボックスの作成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- dialog boxes, creating
- modal dialog boxes, logon screens
- logon screens
ms.assetid: 54823c27-1658-4388-bd12-0a1ce8f3899e
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 1b53c233c13ed53f4cf2ccf489da9af90ae15796
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="creating-a-dialog-box-that-users-cannot-exit"></a>ユーザーが終了できないダイアログ ボックスの作成
ユーザーには終了できない実行時ダイアログ ボックスを作成できます。 この種のダイアログ ボックスはログオンの場合や、アプリケーションやドキュメントをロックする場合に便利です。  
  
### <a name="to-create-a-dialog-box-that-a-user-cannot-exit"></a>ユーザーには終了できないダイアログ ボックスを作成するには  
  
1.  ダイアログ ボックスの **[プロパティ]** ウィンドウで、 **[システム メニュー]** プロパティを **[false]**に設定します。  
  
     これによって、ダイアログ ボックスのシステム メニューと **[閉じる]** ボタンが無効になります。  
  
2.  ダイアログ ボックスのフォームで、 **[キャンセル]** ボタンと **[OK]** ボタンを削除します。  
  
     実行時にユーザーはこれらの特性を持つモーダル ダイアログ ボックスを終了できません。  
  
 この種のダイアログ ボックスをテストできるようにするため、Esc キーが押されると、ダイアログ ボックスのテスト機能がそれを検出します。 (Esc キーは、VK_ESCAPE 仮想キーとも呼ばれます。)実行時にどのように動作するよう設計されているかに関わりなく、テスト モードで Esc キーを押すとダイアログ ボックスは終了します。  
  
> [!NOTE]
>  MFC アプリケーションの場合、ユーザーが終了できないダイアログ ボックスを作成するには、 `OnOK` ボタンと `OnCancel` の既定の動作をオーバーライドする必要があります。それらに関連付けられたボタンを削除しても、Enter キーまたは Esc キーを押せばダイアログ ボックスを終了できるためです。  
  
 マネージ プロジェクトにリソースを追加する方法については、次を参照してください。[デスクトップ アプリでのリソース](/dotnet/framework/resources/index)です。  
  
## <a name="requirements"></a>必要条件  
 Win32  
  
## <a name="see-also"></a>参照  
 [方法: リソースの作成](../windows/how-to-create-a-resource.md)   
 [リソース ファイル (Visual Studio)](../windows/resource-files-visual-studio.md)   
 [ダイアログ エディター](../windows/dialog-editor.md)

