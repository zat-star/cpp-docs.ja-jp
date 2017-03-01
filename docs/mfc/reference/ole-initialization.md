---
title: "OLE の初期化 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.mfc.macros.ole
dev_langs:
- C++
helpviewer_keywords:
- OLE initialization
ms.assetid: aa8a54a7-24c3-4344-b2c6-dbcf6084fa31
caps.latest.revision: 13
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
ms.sourcegitcommit: 17a158366f94d27b7a46917282425d652e6b9042
ms.openlocfilehash: 5c2d8a1552b8cd546b7e22683fe9f73bbc54df5c
ms.lasthandoff: 02/24/2017

---
# <a name="ole-initialization"></a>OLE の初期化
アプリケーションが OLE システム サービスを使用する前に OLE システム Dll を初期化する必要があり、Dll が適切なバージョンであることを確認します。 **AfxOleInit**関数は、OLE システム Dll を初期化します。  
  
### <a name="ole-initialization"></a>OLE の初期化  
  
|||  
|-|-|  
|[AfxOleInit](#afxoleinit)|OLE ライブラリを初期化します。|  
  
##  <a name="a-nameafxoleinita--afxoleinit"></a><a name="afxoleinit"></a>AfxOleInit  
 アプリケーションの OLE サポートを初期化します。  
  
``` 
BOOL AFXAPI AfxOleInit(); 
```  
  
### <a name="return-value"></a>戻り値  
 成功した場合は 0 以外の値です。初期化に失敗した場合は 0 です。失敗の原因は多くの場合、正しくないバージョンの OLE システム DLL がインストールされていることです。  
  
### <a name="remarks"></a>コメント  
 MFC アプリケーションに対する OLE サポートを初期化するには、この関数を呼び出します。 この関数を呼び出すと、次のアクションが発生します。  
  
-   呼び出し元のアプリケーションの現在のアパートメントで COM ライブラリを初期化します。 詳細については、次を参照してください。 [OleInitialize](http://msdn.microsoft.com/library/windows/desktop/ms690134)します。  
  
-   メッセージ フィルター オブジェクトを作成を実装する、 [IMessageFilter](http://msdn.microsoft.com/library/windows/desktop/ms693740)インターフェイスです。 このメッセージ フィルターへの呼び出しでアクセスできる[AfxOleGetMessageFilter](http://msdn.microsoft.com/library/36cca011-4775-4086-b471-5557a87b266c)します。  
  
> [!NOTE]
>  場合**AfxOleInit**と呼ばれますが、MFC DLL からの呼び出しは失敗します。 この関数は DLL から呼び出された場合、呼び出し元アプリケーションによって OLE システムが既に初期化されていることを想定するため、失敗が生じます。  
  
> [!NOTE]
>  MFC アプリケーションは、シングルスレッド アパートメント (STA) として初期化する必要があります。 呼び出した場合[CoInitializeEx](http://msdn.microsoft.com/library/windows/desktop/ms695279)で、`InitInstance`指定をオーバーライド`COINIT_APARTMENTTHREADED`(なく`COINIT_MULTITHREADED`)。 詳細については、[prb] を参照してください: MFC アプリケーションとして、マルチ スレッド アパートメント (828643) でアプリケーションを初期化するときの応答を停止[http://support.microsoft.com/default.aspxscid=kb;en-us;828643](http://support.microsoft.com/default.aspxscid=kb;en-us;828643)します。  

### <a name="requirements"></a>要件  
 **ヘッダー :** afxdisp.h

## <a name="see-also"></a>関連項目  
 [マクロとグローバル](../../mfc/reference/mfc-macros-and-globals.md)

