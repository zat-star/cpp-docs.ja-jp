---
title: "ATL プロジェクトで MFC サポート |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: vc.atl.addmfc
dev_langs: C++
helpviewer_keywords: ATL projects, MFC support
ms.assetid: f90b4276-cb98-4c11-902c-9ebcfe6f954b
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 0217c62ff207ad706dbcb1cd172e878c2b96daee
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="mfc-support-in-atl-projects"></a>ATL プロジェクトで MFC サポート
選択した場合**サポート MFC** ATL プロジェクト ウィザードで、プロジェクトが MFC アプリケーション オブジェクト (クラス) としてアプリケーションを宣言します。 プロジェクトが MFC ライブラリを初期化し、クラスをインスタンス化 (クラス*ProjName*) から派生する[CWinApp](../../mfc/reference/cwinapp-class.md)です。  
  
 このオプションは、属性なしの ATL DLL プロジェクトのみで使用可能です。  
  
```  
class CProjNameApp : public CWinApp  
{  
public:  
 
// Overrides  
    virtual BOOL InitInstance();
virtual int ExitInstance();
DECLARE_MESSAGE_MAP() 
};  
 
BEGIN_MESSAGE_MAP(CProjNameApp, CWinApp)  
END_MESSAGE_MAP()  
 
CProjNameApp theApp;  
 
BOOL CProjNameApp::InitInstance()  
{  
    return CWinApp::InitInstance();

}  
 
int CProjNameApp::ExitInstance()  
{  
    return CWinApp::ExitInstance();

}  
```  
  
 アプリケーションは、オブジェクト クラスを表示して、その`InitInstance`と`ExitInstance`クラス ビュー内の関数。  
  
## <a name="see-also"></a>関連項目  
 [クラスの追加](../../ide/adding-a-class-visual-cpp.md)   
 [ATL プロジェクトの作成](../../atl/reference/creating-an-atl-project.md)   
 [ATL プロジェクトの既定の構成](../../atl/reference/default-atl-project-configurations.md)

