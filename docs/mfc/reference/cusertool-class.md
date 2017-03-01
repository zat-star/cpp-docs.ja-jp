---
title: "CUserTool クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CUserTool
dev_langs:
- C++
helpviewer_keywords:
- CUserTool class
ms.assetid: 7c287d3e-d012-488d-b4e1-aa0f83f294bb
caps.latest.revision: 25
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 2e0b082be6aac7314d8251f89b42ed09e44e2f3d
ms.lasthandoff: 02/24/2017

---
# <a name="cusertool-class"></a>CUserTool クラス
ユーザー ツールは、外部アプリケーションを実行するメニュー項目です。 **ツール**のタブ、**カスタマイズ** ダイアログ ボックス ( [CMFCToolBarsCustomizeDialog クラス](../../mfc/reference/cmfctoolbarscustomizedialog-class.md)) により、ユーザーはユーザー ツールを追加し、名前、コマンド、引数、および各ユーザー ツールの初期ディレクトリを指定します。  
  
## <a name="syntax"></a>構文  
  
```  
class CUserTool : public CObject  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CUserTool::CopyIconToClipboard](#copyicontoclipboard)||  
|[CUserTool::DrawToolIcon](#drawtoolicon)|指定した四角形でユーザーの [ツール] アイコンを描画します。|  
|[CUserTool::GetCommand](#getcommand)|ユーザー ツールに関連付けられているコマンドのテキストを含む文字列を返します。|  
|[CUserTool::GetCommandId](#getcommandid)|ユーザー ツールのメニュー項目のコマンド ID を返します。|  
|[Cusertool:](#invoke)|ユーザー ツールに関連付けられているコマンドを実行します。|  
|[CUserTool::Serialize](#serialize)|アーカイブに対して、このオブジェクトの読み取りまたは書き込みを行います。 (上書き[指定](../../mfc/reference/cobject-class.md#serialize))。|  
|[CUserTool::SetCommand](#setcommand)|ユーザー ツールに関連付けられているコマンドを設定します。|  
|[CUserTool::SetToolIcon](#settoolicon)|このツールに関連付けられているアプリケーションからユーザー ツールのアイコンを読み込みます。|  
  
### <a name="protected-methods"></a>プロテクト メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CUserTool::LoadDefaultIcon](#loaddefaulticon)|ユーザー ツールの既定のアイコンを読み込みます。|  
  
### <a name="data-members"></a>データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CUserTool::m_strArguments](#m_strarguments)|ユーザー ツールのコマンドライン引数。|  
|[CUserTool::m_strInitialDirectory](#m_strinitialdirectory)|ユーザー ツールの起動ディレクトリ。|  
|[CUserTool::m_strLabel](#m_strlabel)|このツールのメニュー項目に表示されるツールの名前。|  
  
## <a name="remarks"></a>コメント  
 アプリケーションでユーザー ツールを有効にする方法の詳細については、次を参照してください。 [CUserToolsManager クラス](../../mfc/reference/cusertoolsmanager-class.md)します。  
  
## <a name="example"></a>例  
 次の例では、ツールの作成、`CUserToolsManager`オブジェクト、設定、`m_strLabel`メンバー変数とユーザー ツールを実行するアプリケーションを設定します。 このコード スニペットの一部である、 [Visual Studio のデモのサンプル](../../visual-cpp-samples.md)します。  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo&#35;](../../mfc/codesnippet/cpp/cusertool-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CUserTool](../../mfc/reference/cusertool-class.md)  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxusertool.h  
  
##  <a name="a-namecopyicontoclipboarda--cusertoolcopyicontoclipboard"></a><a name="copyicontoclipboard"></a>CUserTool::CopyIconToClipboard  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL CopyIconToClipboard();
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-namedrawtoolicona--cusertooldrawtoolicon"></a><a name="drawtoolicon"></a>CUserTool::DrawToolIcon  
 指定した四角形の中心にユーザー ツールのアイコンを描画します。  
  
```  
void DrawToolIcon(
    CDC* pDC,  
    const CRect& rectImage);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
 デバイス コンテキストへのポインター。  
  
 [入力] `rectImage`  
 アイコンを表示する領域の座標を指定します。  
  
##  <a name="a-namegetcommanda--cusertoolgetcommand"></a><a name="getcommand"></a>CUserTool::GetCommand  
 ユーザー ツールに関連付けられているコマンドのテキストを含む文字列を返します。  
  
```  
const CString& GetCommand() const;  
```  
  
### <a name="return-value"></a>戻り値  
 参照を`CString`ユーザー ツールに関連付けられているコマンドのテキストを含むオブジェクト。  
  
##  <a name="a-namegetcommandida--cusertoolgetcommandid"></a><a name="getcommandid"></a>CUserTool::GetCommandId  
 ユーザー ツールのコマンド ID を返します。  
  
```  
UINT GetCommandId() const;  
```  
  
### <a name="return-value"></a>戻り値  
 このユーザー ツールのコマンド ID。  
  
##  <a name="a-nameinvokea--cusertoolinvoke"></a><a name="invoke"></a>Cusertool:  
 ユーザー ツールに関連付けられているコマンドを実行します。  
  
```  
virtual BOOL Invoke();
```  
  
### <a name="return-value"></a>戻り値  
 コマンドが正常に実行された場合は 0 以外それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 呼び出し[ShellExecute](http://msdn.microsoft.com/library/windows/desktop/bb762153)ユーザー ツールに関連付けられているコマンドを実行します。 コマンドが空の場合、または場合に、関数が失敗した[ShellExecute](http://msdn.microsoft.com/library/windows/desktop/bb762153)は失敗します。  
  
##  <a name="a-nameloaddefaulticona--cusertoolloaddefaulticon"></a><a name="loaddefaulticon"></a>CUserTool::LoadDefaultIcon  
 ユーザー ツールの既定のアイコンを読み込みます。  
  
```  
virtual HICON LoadDefaultIcon();
```  
  
### <a name="return-value"></a>戻り値  
 読み込まれたアイコンへのハンドル ( `HICON`)、または`NULL`場合は、既定のアイコンを読み込むことができません。  
  
### <a name="remarks"></a>コメント  
 フレームワークは、ツールの実行可能ファイルからユーザー定義のツールのアイコンを読み込むことがない場合に、このメソッドを呼び出します。  
  
 独自の既定ツール アイコンを指定するには、このメソッドをオーバーライドします。  
  
##  <a name="a-namemstrargumentsa--cusertoolmstrarguments"></a><a name="m_strarguments"></a>CUserTool::m_strArguments  
 ユーザー ツールのコマンドライン引数。  
  
```  
CString m_strArguments;  
```  
  
### <a name="remarks"></a>コメント  
 呼び出したときに、この文字列が、ツールに渡される[cusertool:](#invoke)またはユーザーがこのツールに関連付けられているコマンドをクリックしたとき。  
  
##  <a name="a-namemstrinitialdirectorya--cusertoolmstrinitialdirectory"></a><a name="m_strinitialdirectory"></a>CUserTool::m_strInitialDirectory  
 ユーザー ツールの初期ディレクトリを指定します。  
  
```  
CString m_strInitialDirectory;  
```  
  
### <a name="remarks"></a>コメント  
 この変数は、このツールを呼び出すときに実行される初期ディレクトリを指定します。 [cusertool:](#invoke)またはユーザーがこのツールに関連付けられているコマンドをクリックしたとき。  
  
##  <a name="a-namemstrlabela--cusertoolmstrlabel"></a><a name="m_strlabel"></a>CUserTool::m_strLabel  
 このツールのメニュー項目に表示されるラベルです。  
  
```  
CString m_strLabel;  
```  
  
##  <a name="a-nameserializea--cusertoolserialize"></a><a name="serialize"></a>CUserTool::Serialize  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void Serialize(CArchive& ar);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `ar`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-namesetcommanda--cusertoolsetcommand"></a><a name="setcommand"></a>CUserTool::SetCommand  
 ユーザー ツールを実行するアプリケーションを設定します。  
  
```  
void SetCommand(LPCTSTR lpszCmd);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `lpszCmd`  
 ユーザー ツールに関連する新しいアプリケーションを指定します。  
  
### <a name="remarks"></a>コメント  
 ユーザー ツールを実行する新しいアプリケーションに設定するには、このメソッドを呼び出します。 このメソッドは、古いアイコンを破棄し、特定のアプリケーションからは新しいアイコンを読み込みます。 呼び出してユーザー ツールの既定のアイコンを読み込む場合は、アプリケーションからそのアイコンを読み込むことができません、 [CUserTool::LoadDefaultIcon](#loaddefaulticon)します。  
  
##  <a name="a-namesettoolicona--cusertoolsettoolicon"></a><a name="settoolicon"></a>CUserTool::SetToolIcon  
 このツールを使用するアプリケーションからユーザー ツールのアイコンを読み込みます。  
  
```  
virtual HICON SetToolIcon();
```  
  
### <a name="return-value"></a>戻り値  
 読み込まれたアイコンへのハンドル。  
  
### <a name="remarks"></a>コメント  
 メニュー項目に表示されるアイコンの読み込みには、このメソッドを呼び出します。 このメソッドは、このツールを使用する実行可能ファイルにあるアイコンを検索します。 アイコンがによって提供される場合は、既定のアイコンがない、 [CUserTool::LoadDefaultIcon](#loaddefaulticon)代わりに使用されます。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CWinAppEx クラス](../../mfc/reference/cwinappex-class.md)   
 [CUserToolsManager クラス](../../mfc/reference/cusertoolsmanager-class.md)

