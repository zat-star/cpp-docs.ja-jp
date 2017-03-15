---
title: "DEVNAMES 構造体 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- DEVNAMES
dev_langs:
- C++
helpviewer_keywords:
- DEVNAMES
ms.assetid: aac97f60-2169-471a-ba5d-c0baed9eed9a
caps.latest.revision: 11
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 698a338c94dfa402dd51fa4f683b92a5d30cc0cd
ms.lasthandoff: 02/24/2017

---
# <a name="devnames-structure"></a>DEVNAMES 構造体
`DEVNAMES`構造体には、ドライバー、デバイス、およびプリンターの出力ポート名を識別する文字列が含まれています。  
  
## <a name="syntax"></a>構文  
  
```  
typedef struct tagDEVNAMES { /* dvnm */  
    WORD wDriverOffset;  
    WORD wDeviceOffset;  
    WORD wOutputOffset;  
    WORD wDefault; */* driver,
    device,
    and port-name strings follow wDefault */  
} DEVNAMES;  
```  
  
#### <a name="parameters"></a>パラメーター  
 *wDriverOffset*  
 (入力/出力)デバイス ドライバーのファイル名 (拡張子なし) を表す null で終わる文字列への文字、オフセットを指定します。 入力にこの文字列を使用して、ダイアログ ボックスで最初に表示するプリンターを決めます。  
  
 *wDeviceOffset*  
 (入力/出力)デバイスの名前を表す null で終わる文字列 (最大 32 バイトを null を含む) を文字単位のオフセットを指定します。 この文字列と同一である、 **dmDeviceName**のメンバー、 [DEVMODE](http://msdn.microsoft.com/library/windows/desktop/dd183565)構造体。  
  
 *wOutputOffset*  
 (入力/出力)物理出力メディア (出力ポート) の DOS デバイス名を表す null で終わる文字列への文字、オフセットを指定します。  
  
 *時*  
 文字列が含まれているかどうかを示す、`DEVNAMES`構造体は、通常使うプリンターを識別します。 この文字列を使用して、最後の印刷操作通常使うプリンターが変更されていないことが確認されます。 入力、**時**フラグが設定されて、その他の値、`DEVNAMES`構造体は、現在の既定のプリンターに照らして確認されます。 文字列が一致しない場合、ドキュメントは、形式を変更する必要があるユーザーに知らせる警告メッセージが表示されます。 出力では、**時**印刷のセットアップ ダイアログ ボックスが表示され、ユーザーが ok ボタンを選択した場合にのみ、メンバーが変更されました。 **時**通常使うプリンターを選択した場合、フラグが設定されています。 特定のプリンターを選択すると、フラグが設定されていません。 このメンバーの他のすべてのビットは、[印刷] ダイアログ ボックス プロシージャで内部使用のために予約されています。  
  
## <a name="remarks"></a>コメント  
 **PrintDlg**関数では、これらの文字列を使用して、システム定義の印刷 ダイアログ ボックスでメンバーを初期化します。 ユーザーは、ダイアログ ボックスを閉じ、この構造体で、選択したプリンターに関する情報が返されます。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** commdlg.h  
  
## <a name="see-also"></a>関連項目  
 [構造体、スタイル、コールバック、およびメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CPrintDialog::CreatePrinterDC](../../mfc/reference/cprintdialog-class.md#createprinterdc)



