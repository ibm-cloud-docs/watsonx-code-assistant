---

copyright:
   years: 2024, 2025
lastupdated: "2025-06-26"

keywords: 

subcollection: watsonx-code-assistant

content-type:

---

{{site.data.keyword.attribute-definition-list}}

# Assisted fixes reference
{: #wca-assisted-fixes-reference}

[{{site.data.keyword.wca_short}}]{: tag-blue} [Standard plan]{: tag-purple}

When you modernize or upgrade your Java application, {{site.data.keyword.wca_short}} assists you by providing suggestions in the chat on how to change your code. This reference lists the code issues that are associated with assisted fixes.
{: shortdesc}

For more information, see:
- [Completing assisted fixes when you modernize Java applications](/docs/watsonx-code-assistant?topic=watsonx-code-assistant-wca-modernize-java#wca-modernize-assistedfix)
- [Completing assisted fixes when you upgrade Java applications](/docs/watsonx-code-assistant?topic=watsonx-code-assistant-wca-upgrade-java#wca-upgrade-assistedfix)

## Issues when you modernize WebSphere Application Server to Liberty
{: #wca-assisted-fixes-reference-modernizing}

- `The WebSphere ServletChain API was superseded by a newer implementation`
- `The WebSphere Servlet API was superseded by a newer implementation (match criteria: com.ibm.websphere.servlet.response.ResponseUtils)`
- `The WebSphere Startup Beans Service API was superseded by a newer implementation`
- `The WebSphere Servlet API was superseded by a newer implementation (ServletInputStreamAdapter)`
- `The WebSphere Servlet API was superseded by a newer implementation (ChainerServlet)`
- `The WebSphere Servlet API was superseded by a newer implementation (ServletOutputStreamAdapter)`
- `The WebSphere Servlet API was superseded by a newer implementation (ResponseErrorReport)`
- `Some WebSphere Security APIs and SPIs are unavailable (security Exception)`
- `Some WebSphere Security APIs and SPIs are unavailable (com.ibm.websphere.crypto)`
- `Review use of the dynamic cache service`

## Issues when you upgrade Java SE version
{: #wca-assisted-fixes-reference-upgrading}

- `Avoid using default charset when the output stream is a PrintStream`
- `The defineAnonymousClass method from sun.misc.Unsafe has been removed`
- `The netscape.javascript.JSObject.getWindow(Applet) method has been removed`
- `The sun.nio.cs.map system property was removed`
- `Behavior change in the javax.management.MBeanOperationInfo constructor`
- `The JavaFX modules were removed from JDK 11`
- `Do not use the removed javax.crypto.ExemptionMechanism.finalize() method`
- `Behavior change in java.util.concurrent.ThreadPoolExecutor.finalize() method`
- `Do not use removed runFinalizersOnExit methods`
- `Check for removed methods on Pack200.Packer and Pack200.Unpacker interfaces`
- `The java.util.jar.Pack200 APIs were removed`
- `Do not use APIs from the com.sun.image.codec.jpeg package`
- `The ObjectInputStream.GetField.get(name, object) method was changed to throw a ClassNotFoundException`
- `Weak named curves have been removed`
- `Do not use com.sun.org.apache JAXP internal classes`
- `Do not use com.sun.org.apache JAXP package names in string literals`
- `Do not use the removed com.sun.java.browser.plugin2.DOM and sun.plugin.dom.DOMObject APIs`
- `Do not override the Path2D getPathIterator methods`
- `Do not use the java.lang.Compiler class`
- `Avoid using the removed RMI Activation package`
- `Do not use the netdoc URL protocol`
- `The java.security.acl package was removed`
- `Do not use the com.sun.awt.SecurityWarning class`
- `Do not use the ThreadGroup.allowThreadSuspension method`
- `The java.awt.peer and java.awt.dnd.peer packages are not accessible`
- `Do not use the removed methods addPropertyChangeListener or removePropertyChangeListener from LogManager`
- `Avoid using the degraded ThreadGroup methods`
- `java.lang.Thread.stop(java.lang.Throwable) is disabled`
- `Avoid using Thread.stop(), Thread.resume(), and Thread.suspend() methods`
- `Check for configuration changes related to the com.ibm.security.auth.module.Krb5LoginModule class`

## Issues when you upgrade Java EE version
{: #wca-assisted-fixes-reference-upgrading-ee}

- `Do not use OpenJPA strings for query hints or properties`
- `OpenJPA and WebSphere JPA configuration properties must be migrated`
- `Check for a behavior change in the InjectionPoint getAnnotated method`
- `Check for a behavior change regarding duplicate elements in web descriptors`
- `The openjpa.jdbc.Schema configuration property must be migrated to the mapping file`
- `Classes that use both the Specializes and Alternative annotations are not injected into other modules`
