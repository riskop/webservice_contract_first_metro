web service, contract first
---------------------------

data structures in a separate XSD (not in the WSDL)

jdk implementation (Metro)

demo of server side message dumping (via system properties)

published via JDK endpoint (standalone application)

http://127.0.0.1:8080/helloservice?wsdl

Soap 1.1 (Metro default)

soap header handler

soap fault demonstration (triggered by "abc" input)

Example input:

<soapenv:Envelope 
xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" 
xmlns:hdr="headerDataSpecification" 
xmlns:dat="http://hello.org/hellopersonservice/1.0/datastructures">
   <soapenv:Header>
   <hdr:HeaderData>this is some info in the soap header</hdr:HeaderData>
   </soapenv:Header>
   <soapenv:Body>
      <dat:HelloPersonServiceRequest>
         <dat:Person>
            <dat:FirstName>abcc</dat:FirstName>
            <dat:LastName>?</dat:LastName>
         </dat:Person>
      </dat:HelloPersonServiceRequest>
   </soapenv:Body>
</soapenv:Envelope>

Output for the above:

<S:Envelope xmlns:S="http://schemas.xmlsoap.org/soap/envelope/">
   <S:Body>
      <HelloPersonServiceResponse xmlns="http://hello.org/hellopersonservice/1.0/datastructures">
         <Greetings>hello dear abcc. Info from soap header: this is some info in the soap header</Greetings>
      </HelloPersonServiceResponse>
   </S:Body>
</S:Envelope>

Junit test with Okhttp
