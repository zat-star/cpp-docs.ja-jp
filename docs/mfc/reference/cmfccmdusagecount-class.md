---
title: "CMFCCmdUsageCount クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCCmdUsageCount
- AFXCMDUSAGECOUNT/CMFCCmdUsageCount
- AFXCMDUSAGECOUNT/CMFCCmdUsageCount::AddCmd
- AFXCMDUSAGECOUNT/CMFCCmdUsageCount::GetCount
- AFXCMDUSAGECOUNT/CMFCCmdUsageCount::HasEnoughInformation
- AFXCMDUSAGECOUNT/CMFCCmdUsageCount::IsFreqeuntlyUsedCmd
- AFXCMDUSAGECOUNT/CMFCCmdUsageCount::Reset
- AFXCMDUSAGECOUNT/CMFCCmdUsageCount::Serialize
- AFXCMDUSAGECOUNT/CMFCCmdUsageCount::SetOptions
dev_langs:
- C++
helpviewer_keywords:
- CMFCCmdUsageCount class
ms.assetid: 9c33b783-37c0-43ea-9f31-3c75e246c841
caps.latest.revision: 20
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
ms.openlocfilehash: b264448af4041139018b181e2255988555267b89
ms.lasthandoff: 02/24/2017

---
# <a name="cmfccmdusagecount-class"></a>CMFCCmdUsageCount クラス
など、ユーザーがメニューから項目を選択すると、Windows メッセージの使用率カウントを追跡します。  
  
## <a name="syntax"></a>構文  
  
```  
class CMFCCmdUsageCount : public CObject  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|||  
|-|-|  
|名前|説明|  
|`CMFCCmdUsageCount::CMFCCmdUsageCount`|既定のコンストラクター|  
|`CMFCCmdUsageCount::~CMFCCmdUsageCount`|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|||  
|-|-|  
|名前|説明|  
|[CMFCCmdUsageCount::AddCmd](#addcmd)|指定されたコマンドに関連付けられているカウンターを&1; つずつ増加します。|  
|[CMFCCmdUsageCount::GetCount](#getcount)|指定されたコマンド ID に関連付けられている使用率カウントを取得します。|  
|[CMFCCmdUsageCount::HasEnoughInformation](#hasenoughinformation)|このオブジェクトが追跡データの最小量を収集するかどうかを決定します。|  
|[CMFCCmdUsageCount::IsFreqeuntlyUsedCmd](#isfreqeuntlyusedcmd)|指定されたコマンドが頻繁に使用されるかどうかを決定します。|  
|[CMFCCmdUsageCount::Reset](#reset)|すべてのコマンドの使用率カウントをクリアします。|  
|[CMFCCmdUsageCount::Serialize](#serialize)|アーカイブからこのオブジェクトを読み取りまたはアーカイブを書き込みます。 (上書き[指定](../../mfc/reference/cobject-class.md#serialize))。|  
|[CMFCCmdUsageCount::SetOptions](#setoptions)|セットの値は共有`CMFCCmdUsageCount`クラスのデータ メンバーです。|  
  
### <a name="data-members"></a>データ メンバー  
  
|||  
|-|-|  
|名前|説明|  
|`m_CmdUsage`|A`CMap`コマンドの使用状況カウントを割り当てるオブジェクト。|  
|`m_nMinUsagePercentage`|頻繁に使用するコマンドの最小使用率。|  
|`m_nStartCount`|このオブジェクトが追跡データの最小量を収集するかどうかを決定するために使用開始カウンターです。|  
|`m_nTotalUsage`|追跡されているすべてのコマンド数。|  
  
### <a name="remarks"></a>コメント  
 `CMFCCmdUsageCount`クラスは、32 ビット符号なし整数のカウンターに各数値の Windows メッセージ識別子をマップします。 `CMFCToolBar`頻繁に使用するツールバー項目を表示するのにには、このクラスを使用します。 詳細については`CMFCToolBar`を参照してください[CMFCToolBar クラス](../../mfc/reference/cmfctoolbar-class.md)します。  
  
 永続化できる`CMFCCmdUsageCount`プログラムの実行の間でデータのクラスです。 使用して、 [CMFCCmdUsageCount::Serialize](#serialize)クラス メンバー データをシリアル化する方法、および[CMFCCmdUsageCount::SetOptions](#setoptions)共有メンバー データを設定します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCCmdUsageCount](../../mfc/reference/cmfccmdusagecount-class.md)  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxcmdusagecount.h  
  
##  <a name="addcmd"></a>CMFCCmdUsageCount::AddCmd  
 指定されたコマンドに関連付けられているカウンターを&1; つずつ増加します。  
  
```  
void AddCmd(UINT uiCmd);
```  
  
### <a name="parameters"></a>パラメーター  
  
|||  
|-|-|  
|パラメーター|説明|  
|[入力] `uiCmd`|インクリメントするコマンドのカウンターを指定します。|  
  
### <a name="remarks"></a>コメント  
 このメソッドは、コマンドの数のマップの構造に新しいエントリを追加`m_CmdUsage`エントリが既に存在しません場合。  
  
 このメソッドでは、次の場合に何もはしません。  
  
-   ツールバーのフレームワークがカスタマイズ モードで (、 [CMFCToolBar::IsCustomizeMode](../../mfc/reference/cmfctoolbar-class.md#iscustomizemode)メソッドが値を返します)。  
  
-   コマンドはサブメニューまたはメニュー区分線を指します ( `uiCmd` equals 0 または-1)。  
  
- `uiCmd`標準のコマンドを表します (グローバル`IsStandardCommand`関数は&0; 以外の値を返します)。  
  
##  <a name="getcount"></a>CMFCCmdUsageCount::GetCount  
 指定されたコマンド ID に関連付けられている使用率カウントを取得します。  
  
```  
UINT GetCount(UINT uiCmd) const;  
```  
  
### <a name="parameters"></a>パラメーター  
  
|||  
|-|-|  
|パラメーター|説明|  
|[入力] `uiCmd`|取得するコマンドのカウンターの ID。|  
  
### <a name="return-value"></a>戻り値  
 指定されたコマンド ID に関連付けられている使用率カウント  
  
##  <a name="hasenoughinformation"></a>CMFCCmdUsageCount::HasEnoughInformation  
 このオブジェクトが追跡データの最小量を受信したかどうかを決定します。  
  
```  
BOOL HasEnoughInformation() const;  
```  
  
### <a name="return-value"></a>戻り値  
 この場合は 0 以外のオブジェクトが最小量の追跡データを受信しましたそれ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、場合に&0; 以外の値を返します合計数`m_nTotalUsage`、追跡されているすべてのコマンドは、最初の数以上`m_nStartCount`します。 既定では、フレームワークは、初期カウントが 0 を設定します。 この値を上書きするを使用して、 [CMFCCmdUsageCount::SetOptions](#setoptions)メソッドです。  
  
 このメソッドを使用して[CMFCMenuBar::IsShowAllCommands](../../mfc/reference/cmfcmenubar-class.md#isshowallcommands)をすべての利用可能なメニュー コマンドを表示するかどうかを判断します。  
  
##  <a name="isfreqeuntlyusedcmd"></a>CMFCCmdUsageCount::IsFreqeuntlyUsedCmd  
 指定されたコマンドが頻繁に使用されるかどうかを決定します。  
  
```  
BOOL IsFreqeuntlyUsedCmd(UINT uiCmd) const;  
```  
  
### <a name="parameters"></a>パラメーター  
  
|||  
|-|-|  
|パラメーター|説明|  
|[入力] `uiCmd`|確認するコマンドを指定します。|  
  
### <a name="return-value"></a>戻り値  
 コマンドが頻繁に使用する場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、場合に 0 を返します合計コマンドの使用法`m_nTotalUsage`0 は、です。 それ以外の場合、このメソッドは、指定したコマンドを使用する割合が最小の割合よりも大きい場合は&0; 以外を返します`m_nMinUsagePercentage`します。 既定では、フレームワークは最小の割合を 5 に設定します。 この値を上書きするを使用して、 [CMFCCmdUsageCount::SetOptions](#setoptions)メソッドです。 最小の割合が 0 の場合は、このメソッドは、指定されたコマンド数が 0 より大きい場合は 0 以外を返します。  
  
 [CMFCToolBar::IsCommandRarelyUsed](../../mfc/reference/cmfctoolbar-class.md#iscommandrarelyused)コマンドはほとんど使用されているかどうかを判断するこのメソッドを使用します。  
  
##  <a name="reset"></a>CMFCCmdUsageCount::Reset  
 すべてのコマンドの使用率カウントをクリアします。  
  
```  
void Reset();
```  
  
### <a name="remarks"></a>コメント  
 コマンドの数のマップの構造からすべてのエントリをクリアするには、このメソッドを呼び出す`m_CmdUsage`、合計のコマンドの使用法をリセットして`m_nTotalUsage`、カウンターを 0 にします。  
  
##  <a name="serialize"></a>CMFCCmdUsageCount::Serialize  
 アーカイブからこのオブジェクトを読み取りまたはアーカイブを書き込みます。  
  
```  
virtual void Serialize(CArchive& ar);
```  
  
### <a name="parameters"></a>パラメーター  
  
|||  
|-|-|  
|パラメーター|説明|  
|[入力] `ar`|A`CArchive`をシリアル化するオブジェクト。|  
  
### <a name="remarks"></a>コメント  
 このメソッドは、コマンドの数のマップの構造をシリアル化`m_CmdUsage`、および合計コマンドの使用法`m_nTotalUsage`、または指定したアーカイブするカウンター。  
  
 シリアル化の例については、次を参照してください。[シリアル化: オブジェクトのシリアル化](../../mfc/serialization-serializing-an-object.md)します。  
  
##  <a name="setoptions"></a>CMFCCmdUsageCount::SetOptions  
 セットの値は共有`CMFCCmdUsageCount`クラスのデータ メンバーです。  
  
```  
static BOOL __stdcall SetOptions(
    UINT nStartCount,  
    UINT nMinUsagePercentage);
```  
  
### <a name="parameters"></a>パラメーター  
  
|||  
|-|-|  
|パラメーター|説明|  
|[入力] `nStartCount`|追跡されているすべてのコマンドの新規の初期数。|  
|[入力] `nMinUsagePercentage`|新しい最小使用率。|  
  
### <a name="return-value"></a>戻り値  
 `TRUE`メソッドが成功すると、`FALSE`場合、`nMinUsagePercentage`よりも大きいか、または 100 になります。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、共有設定`CMFCCmdUsageCount`クラスのデータ メンバー`m_nStartCount`と`m_nMinUsagePercentage`に`nStartCount`と`nMinUsagePercentage`、それぞれします。 `m_nStartCount`によって使用される、 [CMFCCmdUsageCount::HasEnoughInformation](#hasenoughinformation)メソッドをこのオブジェクトが追跡データの最小量を収集するかどうかを決定します。 `m_nMinUsagePercentage`によって使用される、 [CMFCCmdUsageCount::IsFreqeuntlyUsedCmd](#isfreqeuntlyusedcmd)指定されたコマンドが頻繁に使用されるかどうかを決定する方法です。  
  
 デバッグ ビルドでこのメソッドを生成、アサーション エラー、`nMinUsagePercentage`よりも大きいか、または 100 になります。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CMFCToolBar クラス](../../mfc/reference/cmfctoolbar-class.md)

