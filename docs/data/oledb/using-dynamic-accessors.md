---
title: "動的アクセサーの使用 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "アクセサー [C++], 動的"
  - "動的アクセサー"
ms.assetid: e5d5bfa6-2b1d-49d0-8ced-914666422431
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# 動的アクセサーの使用
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

動的アクセサーを使用すると、データベース スキーマ \(基になる構造\) が不明な場合でもデータ ソースにアクセスできます。  OLE DB テンプレート ライブラリには、動的アクセサーの使用に役立つクラスがいくつか用意されています。  
  
 [DynamicConsumer](http://msdn.microsoft.com/ja-jp/2ccc4c61-6749-4e83-aa81-00f8009c0dc3) のサンプルには、動的アクセサー クラスを使用して、列情報を取得し、アクセサーを動的に作成する方法が示されています。  
  
## CDynamicAccessor の使い方  
 [CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md) を使用すると、データベース スキーマ \(データベースの基本的な構造\) を理解していない場合でも、データ ソースにアクセスできます。  `CDynamicAccessor` メソッドは、列名、列数、およびデータ型などの列情報を取得します。  この列の情報は、実行時にアクセサーを動的に作成するときに使用します。  列情報は、このクラスによって作成および管理されるバッファーに格納されます。  [GetValue](../../data/oledb/cdynamicaccessor-getvalue.md) メソッドを使用してバッファーからデータを取得します。  
  
## 例  
  
### コード  
  
```  
// Using_Dynamic_Accessors.cpp  
// compile with: /c /EHsc  
#include <stdio.h>  
#include <objbase.h>  
#include <atldbcli.h>  
  
int main( int argc, char* argv[] )  
{  
    HRESULT hr = CoInitialize( NULL );  
  
    CDataSource ds;  
    CSession ss;  
  
    CTable<CDynamicAccessor> rs;  
  
    // The following is an example initialization string:  
    hr = ds.OpenFromInitializationString(L"Provider=SQLOLEDB.1;"  
      L"Integrated Security=SSPI;Persist Security Info=False;"  
      L"Initial Catalog=Loginname;Data Source=your_data_source;"  
      L"Use Procedure for Prepare=1;Auto Translate=True;"  
      L"Packet Size=4096;Workstation ID=LOGINNAME01;"  
      L"Use Encryption for Data=False;"  
      L"Tag with column collation when possible=False");  
  
    hr = ss.Open( ds );  
    hr = rs.Open( ss, "Shippers" );  
  
    hr = rs.MoveFirst( );  
    while( SUCCEEDED( hr ) && hr != DB_S_ENDOFROWSET )  
    {  
        for( size_t i = 1; i <= rs.GetColumnCount( ); i++ )  
        {  
            DBTYPE type;  
            rs.GetColumnType( i, &type );  
            printf_s( "Column %d [%S] is of type %d\n",  
                      i, rs.GetColumnName( i ), type );   
  
            switch( type )  
            {  
                case DBTYPE_WSTR:  
                    printf_s( "value is %S\n",  
                              (WCHAR*)rs.GetValue( i ) );  
                break;  
                case DBTYPE_STR:  
                    printf_s( "value is %s\n",  
                              (CHAR*)rs.GetValue( i ) );  
                default:  
                    printf_s( "value is %d\n",  
                              *(long*)rs.GetValue( i ) );  
            }  
        }  
        hr = rs.MoveNext( );  
    }  
  
    rs.Close();     
    ss.Close();  
    ds.Close();  
    CoUninitialize();  
  
    return 0;  
}  
```  
  
## CDynamicStringAccessor の使い方  
 [CDynamicStringAccessor](../../data/oledb/cdynamicstringaccessor-class.md) は、1 つの重要な点を除いて [CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md) と同様に動作します。  `CDynamicAccessor` はプロバイダーによって報告されたネイティブな形式でデータを要求しますが、`CDynamicStringAccessor` はアクセスされるすべてのデータをデータ ストアから文字列データとしてフェッチするようにプロバイダーに要求します。  これは、特にデータ ストアのコンテンツの表示または印刷などのように、データ ストアの値の計算を要求しない単純なタスクで役に立ちます。  
  
 列情報を取得するには `CDynamicStringAccessor` メソッドを使用します。  この列の情報は、実行時にアクセサーを動的に作成するときに使用します。  列情報は、このクラスによって作成および管理されるバッファーに格納されます。  バッファーからデータを取得するには、[CDynamicStringAccessor::GetString](../Topic/CDynamicStringAccessor::GetString.md) を使用します。また、データをバッファーに格納するには、[CDynamicStringAccessor::SetString](../../data/oledb/cdynamicstringaccessor-setstring.md) を使用します。  
  
## 例  
  
### コード  
  
```  
// Using_Dynamic_Accessors_b.cpp  
// compile with: /c /EHsc  
#include <stdio.h>  
#include <objbase.h>  
#include <atldbcli.h>  
  
int main( int argc, char* argv[] )  
{  
    HRESULT hr = CoInitialize( NULL );  
    if (hr != S_OK)  
    {  
        exit (-1);  
    }  
  
    CDataSource ds;  
    CSession ss;  
  
    CTable<CDynamicStringAccessor> rs;  
  
    // The following is an example initialization string:  
    hr = ds.OpenFromInitializationString(L"Provider=SQLOLEDB.1;"  
      L"Integrated Security=SSPI;Persist Security Info=False;"  
      L"Initial Catalog=Loginname;Data Source=your_data_source;"  
      L"Use Procedure for Prepare=1;Auto Translate=True;"  
      L"Packet Size=4096;Workstation ID=LOGINNAME01;"  
      L"Use Encryption for Data=False;"  
      L"Tag with column collation when possible=False");  
  
    hr = ss.Open( ds );  
    hr = rs.Open( ss, "Shippers" );  
  
    hr = rs.MoveFirst( );  
    while( SUCCEEDED( hr ) && hr != DB_S_ENDOFROWSET )  
    {  
        for( size_t i = 1; i <= rs.GetColumnCount( ); i++ )  
        {  
            printf_s( "column %d value is %s\n",   
                      i, rs.GetString( i ) );  
        }  
        hr = rs.MoveNext( );  
    }  
  
    rs.Close();     
    ss.Close();  
    ds.Close();  
    CoUninitialize();  
  
   return 0;  
  
}  
```  
  
## CDynamicParameterAccessor の使い方  
 [CDynamicParameterAccessor](../../data/oledb/cdynamicparameteraccessor-class.md) は [CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md) と同様ですが、`CDynamicParameterAccessor` は [ICommandWithParameters](https://msdn.microsoft.com/en-us/library/ms712937.aspx) インターフェイスを呼び出すことで設定されるパラメーター情報を取得する点が異なります。  コンシューマーがこのクラスを使用するには、プロバイダーで `ICommandWithParameters` がサポートされている必要があります。  
  
 パラメーター情報は、このクラスによって作成および管理されるバッファーに格納されます。  パラメーター データは、[CDynamicParameterAccessor::GetParam](../Topic/CDynamicParameterAccessor::GetParam.md) と [CDynamicParameterAccessor::GetParamType](../../data/oledb/cdynamicparameteraccessor-getparamtype.md) を使用してバッファーから取得します。  
  
 このクラスを使用して SQL Server のストアド プロシージャを実行し、出力パラメーター値を取得する方法の例については、サポート技術情報の「HOWTO: Execute Stored Procedure Using CDynamicParmeterAccesor \(Q198519\)」を参照してください。サポート技術情報の文書は、MSDN ライブラリの Visual Studio のドキュメントで使用したり、です [http:\/\/support.microsoft.com](http://support.microsoft.com/)。  
  
## 参照  
 [アクセサーの使用](../../data/oledb/using-accessors.md)   
 [CDynamicAccessor クラス](../../data/oledb/cdynamicaccessor-class.md)   
 [CDynamicStringAccessor クラス](../../data/oledb/cdynamicstringaccessor-class.md)   
 [CDynamicParameterAccessor クラス](../../data/oledb/cdynamicparameteraccessor-class.md)   
 [DynamicConsumer Sample](http://msdn.microsoft.com/ja-jp/2ccc4c61-6749-4e83-aa81-00f8009c0dc3)