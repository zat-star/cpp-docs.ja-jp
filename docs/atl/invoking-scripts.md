---
title: "スクリプト (ATL) の呼び出し |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: StringRegister
dev_langs: C++
helpviewer_keywords:
- StringRegister method
- scripts, invoking registry in ATL
ms.assetid: eabd41ee-586b-4266-9e92-5aaad04b73a4
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 7cbf969f601bd90e84bf0ee15ae2ea3dcb392610
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="invoking-scripts"></a>スクリプトの呼び出し
[置き換え可能パラメーター (レジストラーのプリプロセッサ) を使用して](../atl/using-replaceable-parameters-the-registrar-s-preprocessor.md)置換マップをについて説明し、特記レジストラー メソッド**AddReplacement**です。 レジストラーは、スクリプトに固有の他の 8 つのメソッドを持ち、すべては、次の表で説明します。  
  
|メソッド|構文/説明|  
|------------|-------------------------|  
|**ResourceRegister**|**HRESULT ResourceRegister (LPCOLESTR***resFileName* **、UINT** `nID` **、LPCOLESTR** `szType` **) です。** <br /><br /> モジュールのリソースに含まれるスクリプトを登録します。 *resFileName*モジュール自体への UNC パスを示します。 `nID`および`szType`リソースの ID の型をそれぞれ含まれます。|  
|**ResourceUnregister**|**HRESULT ResourceUnregister (LPCOLESTR***resFileName* **、UINT** `nID` **、LPCOLESTR** `szType` **) です。** <br /><br /> モジュールのリソースに含まれるスクリプトを登録解除します。 *resFileName*モジュール自体への UNC パスを示します。 `nID`および`szType`リソースの ID の型をそれぞれ含まれます。|  
|**ResourceRegisterSz**|**HRESULT ResourceRegisterSz (LPCOLESTR***resFileName* **、LPCOLESTR***szID* **、LPCOLESTR** `szType` **);** <br /><br /> モジュールのリソースに含まれるスクリプトを登録します。 *resFileName*モジュール自体への UNC パスを示します。 *szID*と`szType`リソースの文字列識別子と型をそれぞれ含まれます。|  
|**ResourceUnregisterSz**|**HRESULT ResourceUnregisterSz (LPCOLESTR***resFileName* **、LPCOLESTR***szID* **、LPCOLESTR** `szType` **);** <br /><br /> モジュールのリソースに含まれるスクリプトを登録解除します。 *resFileName*モジュール自体への UNC パスを示します。 *szID*と`szType`リソースの文字列識別子と型をそれぞれ含まれます。|  
|**FileRegister**|**HRESULT FileRegister (LPCOLESTR***fileName***) です。** <br /><br /> ファイルにスクリプトを登録します。 *fileName*が含まれています (または) リソース スクリプト ファイルを UNC パスです。|  
|**FileUnregister**|**HRESULT FileUnregister (LPCOLESTR***fileName***) です。** <br /><br /> ファイル内のスクリプトを登録解除します。 *fileName*が含まれています (または) リソース スクリプト ファイルを UNC パスです。|  
|**StringRegister**|**HRESULT StringRegister (LPCOLESTR***データ***) です。** <br /><br /> 文字列内のスクリプトを登録します。 *データ*スクリプト自体が含まれています。|  
|**StringUnregister**|**HRESULT StringUnregister (LPCOLESTR***データ***) です。** <br /><br /> 文字列内のスクリプトを登録解除します。 *データ*スクリプト自体が含まれています。|  
  
 **ResourceRegisterSz**と**ResourceUnregisterSz**のような**ResourceRegister**と**ResourceUnregister**を指定することが、文字列の識別子です。  
  
 メソッド**FileRegister**と**FileUnregister**はリソース内のスクリプトしたくない場合、または独自のファイル内のスクリプトの場合に便利です。 メソッド**StringRegister**と**StringUnregister** .rgs ファイルを動的に割り当てられた文字列に格納できるようにします。  
  
## <a name="see-also"></a>参照  
 [レジストラー スクリプトの作成](../atl/creating-registrar-scripts.md)

