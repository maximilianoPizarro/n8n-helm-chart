---
layout: default
title: n8n Helm Chart for Kubernetes & OpenShift
---

<link rel="icon" href="favicon.svg" type="image/svg+xml">
<link rel="alternate icon" href="https://raw.githubusercontent.com/maximilianoPizarro/botpress-helm-chart/main/favicon-152.ico" type="image/x-icon">

<style>
  :root {
    --n8n-primary: #ff6d5a;
    --n8n-secondary: #1a1a2e;
    --n8n-dark: #0f0f23;
    --n8n-light: #f5f5f5;
    --n8n-accent: #ea4b71;
    --n8n-green: #4cd964;
    --n8n-blue: #5b9bd5;
    --n8n-card-bg: #ffffff;
    --n8n-border: #e0e0e0;
    --n8n-text: #333333;
    --n8n-muted: #6b7280;
  }
  body {
    font-family: 'Inter', -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif;
    color: var(--n8n-text);
    margin: 0;
    padding: 0;
  }
  .hero {
    background: linear-gradient(135deg, var(--n8n-secondary) 0%, var(--n8n-dark) 100%);
    color: white;
    padding: 60px 20px;
    text-align: center;
    border-radius: 0 0 20px 20px;
  }
  .hero h1 {
    font-size: 2.5em;
    margin-bottom: 10px;
    font-weight: 800;
  }
  .hero h1 span {
    color: var(--n8n-primary);
  }
  .hero p {
    font-size: 1.2em;
    opacity: 0.9;
    max-width: 700px;
    margin: 0 auto 20px;
  }
  .badges {
    display: flex;
    gap: 8px;
    justify-content: center;
    flex-wrap: wrap;
    margin-top: 20px;
  }
  .cta-buttons {
    display: flex;
    gap: 12px;
    justify-content: center;
    margin-top: 24px;
    flex-wrap: wrap;
  }
  .cta-btn {
    display: inline-block;
    padding: 12px 28px;
    border-radius: 8px;
    text-decoration: none;
    font-weight: 600;
    font-size: 1em;
    transition: transform 0.2s;
  }
  .cta-btn:hover { transform: translateY(-2px); }
  .cta-primary {
    background: var(--n8n-primary);
    color: white;
  }
  .cta-secondary {
    background: transparent;
    color: white;
    border: 2px solid rgba(255,255,255,0.3);
  }
  .section {
    max-width: 960px;
    margin: 40px auto;
    padding: 0 20px;
  }
  .section h2 {
    font-size: 1.8em;
    color: var(--n8n-secondary);
    border-bottom: 3px solid var(--n8n-primary);
    padding-bottom: 8px;
    margin-bottom: 20px;
  }
  .feature-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
    gap: 20px;
    margin: 20px 0;
  }
  .feature-card {
    background: var(--n8n-card-bg);
    border: 1px solid var(--n8n-border);
    border-radius: 12px;
    padding: 24px;
    transition: box-shadow 0.3s, transform 0.2s;
  }
  .feature-card:hover {
    box-shadow: 0 8px 24px rgba(0,0,0,0.1);
    transform: translateY(-4px);
  }
  .feature-card h3 {
    color: var(--n8n-secondary);
    margin-top: 0;
    font-size: 1.2em;
  }
  .feature-card p {
    color: var(--n8n-muted);
    font-size: 0.95em;
    line-height: 1.5;
  }
  .icon-badge {
    display: inline-block;
    width: 40px;
    height: 40px;
    background: linear-gradient(135deg, var(--n8n-primary), var(--n8n-accent));
    border-radius: 10px;
    margin-bottom: 12px;
    line-height: 40px;
    text-align: center;
    font-size: 20px;
    color: white;
  }
  .workflow-card {
    background: var(--n8n-card-bg);
    border: 1px solid var(--n8n-border);
    border-radius: 12px;
    padding: 20px;
    margin: 16px 0;
  }
  .workflow-card h4 {
    color: var(--n8n-secondary);
    margin: 0 0 8px 0;
  }
  .workflow-card .meta {
    display: flex;
    gap: 16px;
    flex-wrap: wrap;
    margin-top: 8px;
  }
  .workflow-card .tag {
    display: inline-block;
    padding: 3px 10px;
    background: #f0f4ff;
    color: var(--n8n-blue);
    border-radius: 12px;
    font-size: 0.8em;
    font-weight: 600;
  }
  .workflow-card .tag.ai { background: #fff0f0; color: var(--n8n-primary); }
  .workflow-card .tag.mcp { background: #f0fff4; color: #059669; }
  .styled-table {
    width: 100%;
    border-collapse: collapse;
    margin: 16px 0;
    font-size: 0.95em;
  }
  .styled-table th, .styled-table td {
    padding: 10px 14px;
    text-align: left;
    border-bottom: 1px solid var(--n8n-border);
  }
  .styled-table th {
    background: var(--n8n-secondary);
    color: white;
    font-weight: 600;
  }
  .styled-table tr:hover { background: #f9fafb; }
  .arch-diagram {
    background: white;
    padding: 20px;
    border-radius: 12px;
    border: 1px solid var(--n8n-border);
    overflow-x: auto;
    text-align: center;
  }
  .install-step {
    display: flex;
    gap: 16px;
    align-items: flex-start;
    margin: 16px 0;
  }
  .step-number {
    flex-shrink: 0;
    width: 36px;
    height: 36px;
    background: var(--n8n-primary);
    color: white;
    border-radius: 50%;
    display: flex;
    align-items: center;
    justify-content: center;
    font-weight: 700;
    font-size: 1em;
  }
  .step-content { flex: 1; }
  .code-block {
    background: #1e1e2e;
    color: #e0e0e0;
    padding: 16px;
    border-radius: 8px;
    overflow-x: auto;
    font-family: 'Fira Code', 'Courier New', monospace;
    font-size: 0.9em;
    line-height: 1.5;
    margin: 8px 0;
  }
  .screenshot-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
    gap: 20px;
    margin: 20px 0;
  }
  .screenshot-card {
    border: 1px solid var(--n8n-border);
    border-radius: 12px;
    overflow: hidden;
    transition: box-shadow 0.3s;
  }
  .screenshot-card:hover {
    box-shadow: 0 8px 24px rgba(0,0,0,0.1);
  }
  .screenshot-card img {
    width: 100%;
    display: block;
    cursor: zoom-in;
  }
  .screenshot-card .caption {
    padding: 12px 16px;
    font-size: 0.9em;
    color: var(--n8n-muted);
    background: var(--n8n-light);
    font-weight: 600;
  }
  .lightbox-overlay {
    display: none;
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background: rgba(0,0,0,0.9);
    z-index: 9999;
    cursor: zoom-out;
    justify-content: center;
    align-items: center;
    padding: 20px;
    box-sizing: border-box;
  }
  .lightbox-overlay.active {
    display: flex;
  }
  .lightbox-overlay img {
    max-width: 95%;
    max-height: 95vh;
    border-radius: 8px;
    box-shadow: 0 0 40px rgba(0,0,0,0.5);
    object-fit: contain;
  }
  .lightbox-close {
    position: fixed;
    top: 16px;
    right: 24px;
    color: white;
    font-size: 36px;
    font-weight: 300;
    cursor: pointer;
    z-index: 10000;
    line-height: 1;
    opacity: 0.8;
    transition: opacity 0.2s;
  }
  .lightbox-close:hover { opacity: 1; }
  .lightbox-caption {
    position: fixed;
    bottom: 20px;
    left: 50%;
    transform: translateX(-50%);
    color: white;
    font-size: 0.95em;
    background: rgba(0,0,0,0.6);
    padding: 8px 20px;
    border-radius: 20px;
    z-index: 10000;
  }
  footer.site-footer {
    background: var(--n8n-secondary);
    color: rgba(255,255,255,0.7);
    text-align: center;
    padding: 30px 20px;
    margin-top: 40px;
    border-radius: 20px 20px 0 0;
  }
  footer.site-footer a { color: var(--n8n-primary); }
</style>

<div class="hero">
  <h1><span>n8n</span> Helm Chart</h1>
  <p>Deploy n8n workflow automation on <strong>Kubernetes</strong> and <strong>Red Hat OpenShift</strong> with native AI capabilities, OpenShift MCP Server integration, and Developer Sandbox support.</p>
  <div class="badges">
    <img src="https://img.shields.io/badge/redhat-CC0000?style=for-the-badge&logo=redhat&logoColor=white" alt="Red Hat">
    <img src="https://img.shields.io/badge/kubernetes-%23326ce5.svg?style=for-the-badge&logo=kubernetes&logoColor=white" alt="Kubernetes">
    <img src="https://img.shields.io/badge/helm-0db7ed?style=for-the-badge&logo=helm&logoColor=white" alt="Helm">
    <a href="https://artifacthub.io/packages/search?repo=n8n-openshift"><img src="https://img.shields.io/endpoint?url=https://artifacthub.io/badge/repository/n8n-openshift" alt="Artifact Hub"></a>
    <a href="https://artifacthub.io/packages/helm/openshift-mcp-server/openshift-mcp-server"><img src="https://img.shields.io/endpoint?url=https://artifacthub.io/badge/repository/openshift-mcp-server" alt="OpenShift MCP Server on Artifact Hub"></a>
    <a href="https://quay.io/repository/maximilianopizarro/n8n"><img src="https://img.shields.io/badge/dynamic/json?url=https%3A%2F%2Fquay.io%2Fapi%2Fv1%2Frepository%2Fmaximilianopizarro%2Fn8n%2Ftag%2F&query=%24.tags.length&suffix=%20tags&label=quay.io&color=EE0000&logo=redhat&logoColor=white" alt="Quay.io Tags"></a>
  </div>
  <div class="cta-buttons">
    <a href="#installation" class="cta-btn cta-primary">Get Started</a>
    <a href="https://github.com/maximilianoPizarro/n8n-helm-chart" class="cta-btn cta-secondary">View on GitHub</a>
  </div>
</div>

<div class="section">
  <h2>Features</h2>
  <div class="feature-grid">
    <div class="feature-card">
      <div class="icon-badge">&#9881;</div>
      <h3>OpenShift Native</h3>
      <p>First-class support for Red Hat OpenShift including Routes, SCCs, and Developer Sandbox compatibility with restricted security contexts.</p>
    </div>
    <div class="feature-card">
      <div class="icon-badge">&#129302;</div>
      <h3>AI-Powered Workflows</h3>
      <p>Integrate with OpenShift AI models like IBM Granite 3.1 via LiteLLM proxy and MCP Server for intelligent infrastructure monitoring.</p>
    </div>
    <div class="feature-card">
      <div class="icon-badge">&#9993;</div>
      <h3>Mailpit Integration</h3>
      <p>Optional built-in Mailpit SMTP test server for previewing email reports from workflows without external email infrastructure.</p>
    </div>
    <div class="feature-card">
      <div class="icon-badge">&#128736;</div>
      <h3>MCP Server Support</h3>
      <p>Connect to OpenShift and Kubernetes MCP Servers to query cluster state, analyze pods, deployments, routes, and security posture.</p>
    </div>
    <div class="feature-card">
      <div class="icon-badge">&#128200;</div>
      <h3>Production Ready</h3>
      <p>Supports queue mode with Valkey/Redis, worker autoscaling, PostgreSQL backend, ServiceMonitor for Prometheus, and HPA.</p>
    </div>
    <div class="feature-card">
      <div class="icon-badge">&#128274;</div>
      <h3>Security First</h3>
      <p>Non-root containers, restricted SCC support, enableServiceLinks control, and proper RBAC with dynamic naming.</p>
    </div>
  </div>
</div>

<script src="https://cdn.jsdelivr.net/npm/mermaid@11/dist/mermaid.min.js"></script>
<script>mermaid.initialize({startOnLoad:true, theme:'base', themeVariables:{primaryColor:'#ff6d5a',primaryTextColor:'#fff',primaryBorderColor:'#ea4b71',lineColor:'#6b7280',secondaryColor:'#1a1a2e',tertiaryColor:'#f5f5f5',fontFamily:'Inter,sans-serif'}});</script>

<div class="section">
  <h2>Architecture</h2>
  <div class="arch-diagram">
    <div class="mermaid">
graph LR
  subgraph HELM["n8n Helm Chart"]
    N8N["🔧 n8n<br/>Workflow Engine<br/><i>n8nio/n8n</i>"]
    MAIL["✉️ Mailpit<br/>SMTP Test Server<br/><i>Optional</i>"]
    PVC["💾 PVC<br/>Persistent Data"]
  end

  subgraph AI["AI & MCP Layer"]
    LITE["🤖 LiteLLM Proxy<br/>OpenAI-compatible"]
    GRANITE["🧠 IBM Granite 3.1 8B"]
    QWEN["🧠 Qwen 3 8B"]
  end

  subgraph MCP["MCP Servers"]
    OSMCP["☸️ OpenShift MCP<br/>Server"]
    K8SMCP["☸️ K8s MCP<br/>Server"]
  end

  K8SAPI["☁️ Kubernetes API"]

  N8N -->|"AI Analysis"| LITE
  N8N -->|"Email Reports"| MAIL
  N8N --- PVC
  LITE --> GRANITE
  LITE --> QWEN
  N8N -->|"MCP Tools"| OSMCP
  N8N -->|"MCP Tools"| K8SMCP
  OSMCP --> K8SAPI
  K8SMCP --> K8SAPI
    </div>
  </div>

  <table class="styled-table">
    <thead>
      <tr><th>Component</th><th>Description</th></tr>
    </thead>
    <tbody>
      <tr><td><strong>n8n</strong></td><td>Workflow automation engine deployed via Helm</td></tr>
      <tr><td><strong>LiteLLM</strong></td><td>OpenAI-compatible proxy routing to Granite/Qwen models</td></tr>
      <tr><td><strong>OpenShift MCP Server</strong></td><td>MCP server exposing OpenShift/Kubernetes API as tools</td></tr>
      <tr><td><strong>K8s MCP Server</strong></td><td>Additional Kubernetes-native MCP tool server</td></tr>
      <tr><td><strong>Mailpit</strong></td><td>Lightweight SMTP test server with web UI (optional)</td></tr>
    </tbody>
  </table>
</div>

<div class="section">
  <h2>Screenshots</h2>

  <h3>All Workflows</h3>
  <div class="screenshot-grid" style="grid-template-columns: 1fr;">
    <div class="screenshot-card">
      <img src="screenshots/n8n-all-workflows-list.png" alt="All 8 OpenShift MCP Workflows">
      <div class="caption">n8n - 8 OpenShift MCP Server Workflows Imported</div>
    </div>
  </div>

  <h3>OpenShift MCP Server Workflow Examples</h3>
  <div class="screenshot-grid">
    <div class="screenshot-card">
      <img src="screenshots/n8n-editor-openshift-pod-monitor-ai-agent-mcp-tools.png" alt="Pod Monitor AI Agent with MCP Tools">
      <div class="caption">1. Pod Monitor - AI Agent with MCP Tools</div>
    </div>
    <div class="screenshot-card">
      <img src="screenshots/n8n-editor-openshift-pod-monitor-mcp-granite-email.png" alt="Pod Monitor MCP + Granite + Email">
      <div class="caption">2. Pod Monitor - MCP + Granite + Email</div>
    </div>
    <div class="screenshot-card">
      <img src="screenshots/n8n-editor-deployment-rollout-status.png" alt="Deployment Rollout Status">
      <div class="caption">3. Deployment Rollout Status</div>
    </div>
    <div class="screenshot-card">
      <img src="screenshots/n8n-editor-resource-quota-monitor.png" alt="Resource Quota Monitor">
      <div class="caption">4. Resource Quota Monitor</div>
    </div>
    <div class="screenshot-card">
      <img src="screenshots/n8n-editor-security-audit.png" alt="Security Audit">
      <div class="caption">5. Security Audit</div>
    </div>
    <div class="screenshot-card">
      <img src="screenshots/n8n-editor-route-tls-expiry.png" alt="Route TLS Expiry Check">
      <div class="caption">6. Route &amp; TLS Expiry Check</div>
    </div>
    <div class="screenshot-card">
      <img src="screenshots/n8n-editor-event-anomaly-detector.png" alt="Event Anomaly Detector">
      <div class="caption">7. Event Anomaly Detector</div>
    </div>
    <div class="screenshot-card">
      <img src="screenshots/n8n-editor-smtp-test-gmail.png" alt="SMTP Test Workflow">
      <div class="caption">SMTP Test - Email via Mailpit</div>
    </div>
  </div>

  <h3>Services</h3>
  <div class="screenshot-grid">
    <div class="screenshot-card">
      <img src="screenshots/n8n-dashboard.png" alt="n8n Dashboard">
      <div class="caption">n8n Dashboard Overview</div>
    </div>
    <div class="screenshot-card">
      <img src="screenshots/mailpit-inbox.png" alt="Mailpit Inbox with OpenShift Reports">
      <div class="caption">Mailpit Inbox - Workflow Email Reports</div>
    </div>
    <div class="screenshot-card">
      <img src="screenshots/mailpit-email-detail.png" alt="Mailpit Email Detail - Pod Status Report">
      <div class="caption">Pod Status Report - HTML Email via Mailpit</div>
    </div>
  </div>

  <h3>MCP Inspector - Tool Verification</h3>
  <div class="screenshot-grid" style="grid-template-columns: 1fr;">
    <div class="screenshot-card">
      <img src="screenshots/mcp-inspector-monitor-deployments.png" alt="MCP Inspector - monitorDeployments tool output">
      <div class="caption">MCP Inspector - monitorDeployments: 11 deployments healthy, 0 issues</div>
    </div>
  </div>
</div>

<div class="section" id="installation">
  <h2>Installation</h2>
  <div class="install-step">
    <div class="step-number">1</div>
    <div class="step-content">
      <strong>Add the Helm repository</strong>
      <div class="code-block">helm repo add n8n-openshift https://maximilianopizarro.github.io/n8n-helm-chart/<br>helm repo update</div>
    </div>
  </div>
  <div class="install-step">
    <div class="step-number">2</div>
    <div class="step-content">
      <strong>Install the chart</strong>
      <div class="code-block">helm install n8n n8n-openshift/n8n --version 1.16.0</div>
    </div>
  </div>
  <div class="install-step">
    <div class="step-number">3</div>
    <div class="step-content">
      <strong>Install on OpenShift Developer Sandbox</strong>
      <div class="code-block">oc login --token=&lt;your-token&gt; --server=https://api.&lt;cluster&gt;.openshiftapps.com:6443<br>helm install n8n n8n-openshift/n8n -f values-sandbox.yaml</div>
    </div>
  </div>
</div>

<div class="section">
  <h2>Developer Sandbox Quick Start</h2>
  <p>For Red Hat OpenShift Developer Sandbox, use these values to ensure compatibility with restricted SCCs:</p>
  <div class="code-block">enableServiceLinks: false<br><br>podSecurityContext: {}<br>securityContext:<br>&nbsp;&nbsp;allowPrivilegeEscalation: false<br>&nbsp;&nbsp;capabilities:<br>&nbsp;&nbsp;&nbsp;&nbsp;drop:<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;- ALL<br>&nbsp;&nbsp;readOnlyRootFilesystem: false<br>&nbsp;&nbsp;runAsNonRoot: true<br><br>route:<br>&nbsp;&nbsp;enabled: true<br>&nbsp;&nbsp;sccRoleDisabled: true<br><br>main:<br>&nbsp;&nbsp;config:<br>&nbsp;&nbsp;&nbsp;&nbsp;n8n:<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;user_folder: "/data"<br>&nbsp;&nbsp;persistence:<br>&nbsp;&nbsp;&nbsp;&nbsp;enabled: true<br>&nbsp;&nbsp;&nbsp;&nbsp;storageClass: gp3-csi<br>&nbsp;&nbsp;&nbsp;&nbsp;size: 2Gi<br>&nbsp;&nbsp;&nbsp;&nbsp;mountPath: "/data"<br>&nbsp;&nbsp;service:<br>&nbsp;&nbsp;&nbsp;&nbsp;type: ClusterIP<br>&nbsp;&nbsp;&nbsp;&nbsp;port: 5678<br><br>mailpit:<br>&nbsp;&nbsp;enabled: true<br>&nbsp;&nbsp;route:<br>&nbsp;&nbsp;&nbsp;&nbsp;enabled: true<br>&nbsp;&nbsp;podSecurityContext: {}</div>

  <table class="styled-table">
    <thead>
      <tr><th>Setting</th><th>Value</th><th>Reason</th></tr>
    </thead>
    <tbody>
      <tr><td><code>enableServiceLinks</code></td><td><code>false</code></td><td>Avoids N8N_PORT env conflict in OpenShift</td></tr>
      <tr><td><code>route.sccRoleDisabled</code></td><td><code>true</code></td><td>Developer Sandbox users cannot create SCC Roles</td></tr>
      <tr><td><code>main.config.n8n.user_folder</code></td><td><code>/data</code></td><td>Writable path for random UID assigned by OpenShift</td></tr>
      <tr><td><code>main.persistence.mountPath</code></td><td><code>/data</code></td><td>Mount PVC at writable path instead of /home/node/.n8n</td></tr>
      <tr><td><code>podSecurityContext</code></td><td><code>{}</code></td><td>No fsGroup (restricted SCC)</td></tr>
      <tr><td><code>main.persistence.storageClass</code></td><td><code>gp3-csi</code></td><td>Sandbox default StorageClass</td></tr>
    </tbody>
  </table>
</div>

<div class="section">
  <h2>OpenShift MCP Server Workflow Examples</h2>
  <p>Each workflow follows a <strong>6-node pipeline</strong> that calls MCP Server tools directly via JSON-RPC, passes real cluster data to an AI model for analysis, and delivers a branded HTML email report through Mailpit:</p>
  <div class="code-block" style="font-size:13px;text-align:center;letter-spacing:0.5px;">Trigger → Set Parameters → <strong>MCP Tool Call</strong> (JSON-RPC) → <strong>AI Analysis</strong> (LiteLLM) → Build HTML Report → Send via Mailpit</div>

  <div class="workflow-card">
    <h4>1. Pod Monitor - AI Agent with MCP Tools</h4>
    <p>Calls <code>pods_list</code> via K8s MCP Server (JSON-RPC over Streamable HTTP) to retrieve all pods in the namespace, then passes the real pod data to Granite/Qwen3 for status analysis and sends a branded HTML email via Mailpit API.</p>
    <div class="meta">
      <span class="tag mcp">MCP: pods_list</span>
      <span class="tag ai">Granite / Qwen3</span>
      <span class="tag">Mailpit</span>
      <span class="tag">Manual Trigger</span>
    </div>
  </div>

  <div class="workflow-card">
    <h4>2. Pod Monitor - MCP + Granite + Email</h4>
    <p>Calls <code>monitorDeployments</code> via Quarkus MCP Server to get deployment health metrics, then uses AI to analyze healthy vs unhealthy deployments, replica mismatches, and sends the report via Mailpit.</p>
    <div class="meta">
      <span class="tag mcp">MCP: monitorDeployments</span>
      <span class="tag ai">Granite / Qwen3</span>
      <span class="tag">Mailpit</span>
      <span class="tag">Manual Trigger</span>
    </div>
  </div>

  <div class="workflow-card">
    <h4>3. Deployment Rollout Status</h4>
    <p>Calls <code>monitorDeployments</code> to retrieve real-time deployment data, then AI analyzes replica health (desired vs available vs ready), rollout strategy, container image versions, and flags deployments with mismatches.</p>
    <div class="meta">
      <span class="tag mcp">MCP: monitorDeployments</span>
      <span class="tag ai">Granite / Qwen3</span>
      <span class="tag">Mailpit</span>
      <span class="tag">Manual Trigger</span>
    </div>
  </div>

  <div class="workflow-card">
    <h4>4. Resource Quota Monitor</h4>
    <p>Calls <code>getPerformanceMetrics</code> via Quarkus MCP Server every 6 hours, then AI analyzes CPU/memory utilization, ResourceQuota limits vs usage, top resource consumers. Flags resources above 80% threshold.</p>
    <div class="meta">
      <span class="tag mcp">MCP: getPerformanceMetrics</span>
      <span class="tag ai">Granite / Qwen3</span>
      <span class="tag">Mailpit</span>
      <span class="tag">Schedule (6h)</span>
    </div>
  </div>

  <div class="workflow-card">
    <h4>5. Security Audit</h4>
    <p>Calls <code>checkClusterHealth</code> via Quarkus MCP Server, then AI performs a security posture assessment following CIS benchmarks: ServiceAccount roles, SCC usage, NetworkPolicy, Secrets audit. Findings classified as PASS, WARNING, or CRITICAL.</p>
    <div class="meta">
      <span class="tag mcp">MCP: checkClusterHealth</span>
      <span class="tag ai">Granite / Qwen3</span>
      <span class="tag">Mailpit</span>
      <span class="tag">Manual Trigger</span>
    </div>
  </div>

  <div class="workflow-card">
    <h4>6. Route &amp; TLS Expiry Check</h4>
    <p>Calls <code>resources_list</code> (resource_type: routes) via K8s MCP Server daily, then AI analyzes route configuration, TLS termination types, and certificate expiry. Alerts on certificates expiring within 30 days.</p>
    <div class="meta">
      <span class="tag mcp">MCP: resources_list</span>
      <span class="tag ai">Granite / Qwen3</span>
      <span class="tag">Mailpit</span>
      <span class="tag">Schedule (daily)</span>
    </div>
  </div>

  <div class="workflow-card">
    <h4>7. Event Anomaly Detector</h4>
    <p>Calls <code>events_list</code> via K8s MCP Server every 30 minutes, then AI detects anomalous Kubernetes Events: repeated warnings, OOMKilled, FailedScheduling, image pull errors. Conditional alerts only when anomalies are found.</p>
    <div class="meta">
      <span class="tag mcp">MCP: events_list</span>
      <span class="tag ai">Granite / Qwen3</span>
      <span class="tag">Mailpit</span>
      <span class="tag">Schedule (30min)</span>
    </div>
  </div>

  <table class="styled-table">
    <thead>
      <tr><th>#</th><th>Workflow</th><th>MCP Tool</th><th>MCP Server</th><th>Trigger</th></tr>
    </thead>
    <tbody>
      <tr><td>1</td><td>Pod Monitor - AI Agent</td><td><code>pods_list</code></td><td>K8s MCP (8085)</td><td>Manual</td></tr>
      <tr><td>2</td><td>Pod Monitor - MCP + Granite</td><td><code>monitorDeployments</code></td><td>Quarkus MCP (8080)</td><td>Manual</td></tr>
      <tr><td>3</td><td>Deployment Rollout Status</td><td><code>monitorDeployments</code></td><td>Quarkus MCP (8080)</td><td>Manual</td></tr>
      <tr><td>4</td><td>Resource Quota Monitor</td><td><code>getPerformanceMetrics</code></td><td>Quarkus MCP (8080)</td><td>Schedule (6h)</td></tr>
      <tr><td>5</td><td>Security Audit</td><td><code>checkClusterHealth</code></td><td>Quarkus MCP (8080)</td><td>Manual</td></tr>
      <tr><td>6</td><td>Route &amp; TLS Expiry</td><td><code>resources_list</code></td><td>K8s MCP (8085)</td><td>Schedule (daily)</td></tr>
      <tr><td>7</td><td>Event Anomaly Detector</td><td><code>events_list</code></td><td>K8s MCP (8085)</td><td>Schedule (30min)</td></tr>
    </tbody>
  </table>

  <p>Find all workflow JSON files in the <a href="https://github.com/maximilianoPizarro/n8n-helm-chart/tree/main/workflows">workflows directory</a> or in the <a href="https://github.com/maximilianoPizarro/n8n-sandbox/tree/main/workflows">n8n-sandbox repository</a>.</p>
</div>

<div class="section">
  <h2>Mailpit Email Output</h2>
  <p>When Mailpit is enabled, n8n workflows can send branded HTML email reports that are captured and viewable in the Mailpit web UI. Configure n8n SMTP credentials to point to the Mailpit service:</p>
  <div class="code-block">main:<br>&nbsp;&nbsp;config:<br>&nbsp;&nbsp;&nbsp;&nbsp;n8n:<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;smtp_host: "&lt;release-name&gt;-mailpit"<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;smtp_port: "1025"<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;smtp_ssl: "false"</div>
  <p>Access the Mailpit web UI via its OpenShift Route to view all captured email reports from your workflows.</p>
  <div class="screenshot-grid">
    <div class="screenshot-card">
      <img src="screenshots/mailpit-inbox.png" alt="Mailpit Inbox with OpenShift Reports">
      <div class="caption">Mailpit Inbox - Workflow Email Reports</div>
    </div>
    <div class="screenshot-card">
      <img src="screenshots/mailpit-email-detail.png" alt="Pod Status Report Email">
      <div class="caption">Pod Status Report - Rendered HTML Email</div>
    </div>
  </div>
</div>

<div class="section">
  <h2>OpenShift MCP Server</h2>
  <p>The workflows above require the <a href="https://artifacthub.io/packages/helm/openshift-mcp-server/openshift-mcp-server">OpenShift MCP Server</a> Helm chart deployed in your cluster. It provides a dual MCP server deployment: a custom Quarkus server (19 operational tools) and the official <a href="https://github.com/openshift/openshift-mcp-server">openshift/openshift-mcp-server</a> (20+ Kubernetes tools), plus an MCP Inspector UI and LiteLLM proxy.</p>
  <div class="badges" style="margin:16px 0;">
    <a href="https://artifacthub.io/packages/helm/openshift-mcp-server/openshift-mcp-server"><img src="https://img.shields.io/endpoint?url=https://artifacthub.io/badge/repository/openshift-mcp-server" alt="OpenShift MCP Server on Artifact Hub"></a>
  </div>
  <div class="install-step">
    <div class="step-number">1</div>
    <div class="step-content">
      <strong>Add the Helm repository</strong>
      <div class="code-block">helm repo add openshift-mcp https://maximilianoPizarro.github.io/openshift-mcp-server<br>helm repo update</div>
    </div>
  </div>
  <div class="install-step">
    <div class="step-number">2</div>
    <div class="step-content">
      <strong>Install the OpenShift MCP Server</strong>
      <div class="code-block">helm install openshift-mcp-server openshift-mcp/openshift-mcp-server \<br>&nbsp;&nbsp;--namespace openshift-lightspeed \<br>&nbsp;&nbsp;--create-namespace \<br>&nbsp;&nbsp;--set namespace=openshift-lightspeed</div>
    </div>
  </div>
  <div class="install-step">
    <div class="step-number">3</div>
    <div class="step-content">
      <strong>Install on Developer Sandbox (same namespace as n8n)</strong>
      <div class="code-block">helm install openshift-mcp-server openshift-mcp/openshift-mcp-server \<br>&nbsp;&nbsp;--set namespace=&lt;your-sandbox-namespace&gt;</div>
    </div>
  </div>

  <table class="styled-table">
    <thead>
      <tr><th>Component</th><th>Port</th><th>Description</th></tr>
    </thead>
    <tbody>
      <tr><td><strong>Quarkus MCP Server</strong></td><td>8080</td><td>19 tools: monitoring, deployment, performance testing</td></tr>
      <tr><td><strong>K8s MCP Server</strong></td><td>8085</td><td>20+ tools: CRUD, pods, helm, events, nodes</td></tr>
      <tr><td><strong>MCP Inspector</strong></td><td>8080</td><td>Web UI for testing MCP tools interactively</td></tr>
      <tr><td><strong>LiteLLM Proxy</strong></td><td>4000</td><td>OpenAI-compatible proxy for Granite/Qwen3 models</td></tr>
    </tbody>
  </table>

  <p>Full documentation: <a href="https://maximilianopizarro.github.io/openshift-mcp-server">maximilianopizarro.github.io/openshift-mcp-server</a></p>
</div>

<div class="section">
  <h2>Configuration</h2>
  <h3>N8n Configuration via Values</h3>
  <p>Configuration under <code>main.config:</code> and <code>main.secret:</code> in <code>values.yaml</code> is transformed 1:1 into Kubernetes ENV variables:</p>
  <div class="code-block">main:<br>&nbsp;&nbsp;config:<br>&nbsp;&nbsp;&nbsp;&nbsp;n8n:<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;encryption_key: "my_secret"&nbsp;&nbsp;# =&gt; N8N_ENCRYPTION_KEY=my_secret<br>&nbsp;&nbsp;&nbsp;&nbsp;db:<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;type: postgresdb&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;# =&gt; DB_TYPE=postgresdb<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;postgresdb:<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;host: 192.168.0.52&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;# =&gt; DB_POSTGRESDB_HOST=192.168.0.52</div>
  <p>Consult the <a href="https://docs.n8n.io/hosting/configuration/environment-variables/">n8n Environment Variables Documentation</a>.</p>

  <h3>Enabling Mailpit</h3>
  <div class="code-block">mailpit:<br>&nbsp;&nbsp;enabled: true<br>&nbsp;&nbsp;route:<br>&nbsp;&nbsp;&nbsp;&nbsp;enabled: true&nbsp;&nbsp;# Expose web UI via OpenShift Route<br>&nbsp;&nbsp;smtp:<br>&nbsp;&nbsp;&nbsp;&nbsp;port: 1025<br>&nbsp;&nbsp;ui:<br>&nbsp;&nbsp;&nbsp;&nbsp;port: 8025</div>

  <h3>Basic Deployment with Ingress</h3>
  <div class="code-block">ingress:<br>&nbsp;&nbsp;enabled: true<br>&nbsp;&nbsp;hosts:<br>&nbsp;&nbsp;&nbsp;&nbsp;- host: n8n.mydomain.com<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;paths:<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;- path: /<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;pathType: Prefix</div>

  <h3>Queue Mode with External Redis</h3>
  <div class="code-block">db:<br>&nbsp;&nbsp;type: postgresdb<br><br>externalPostgresql:<br>&nbsp;&nbsp;host: "postgresql.example.com"<br>&nbsp;&nbsp;username: "n8nuser"<br>&nbsp;&nbsp;password: "secure-password"<br>&nbsp;&nbsp;database: "n8n"<br><br>worker:<br>&nbsp;&nbsp;mode: queue<br><br>externalRedis:<br>&nbsp;&nbsp;host: "redis.example.com"<br>&nbsp;&nbsp;username: "default"<br>&nbsp;&nbsp;password: "secure-password"</div>
</div>

<div class="section">
  <h2>Container Image</h2>
  <p>A Red Hat UBI-based container image is available at <code>quay.io/maximilianopizarro/n8n</code>. It clones the official n8n source, builds it, and runs on a Red Hat certified base image (<code>registry.access.redhat.com/ubi9/nodejs-22</code>).</p>
  <div class="code-block">image:<br>&nbsp;&nbsp;repository: quay.io/maximilianopizarro/n8n<br>&nbsp;&nbsp;tag: "1.123.28"</div>
  <p>The image is built automatically via GitHub Actions on every push to <code>main</code>.</p>
</div>

<div class="section">
  <h2>Requirements</h2>
  <table class="styled-table">
    <thead>
      <tr><th>Requirement</th><th>Version</th></tr>
    </thead>
    <tbody>
      <tr><td>Kubernetes</td><td>&gt;= 1.20.0</td></tr>
      <tr><td>Helm</td><td>&gt;= 3.8</td></tr>
      <tr><td>Database</td><td>SQLite (embedded) or PostgreSQL</td></tr>
    </tbody>
  </table>
  <table class="styled-table">
    <thead>
      <tr><th>Dependency</th><th>Version</th><th>Condition</th></tr>
    </thead>
    <tbody>
      <tr><td>Valkey (Bitnami)</td><td>2.4.7</td><td><code>valkey.enabled</code></td></tr>
    </tbody>
  </table>
</div>


<div class="section">
  <h2>Release Notes</h2>

  <h3>v1.16.0 <span style="font-size:13px;color:var(--n8n-muted);font-weight:400;">(n8n 1.123.28)</span></h3>

  <h4 style="color:var(--n8n-green);margin-top:20px;">Added</h4>
  <ul>
    <li><strong>OpenShift MCP Server integration</strong> — 7 workflows calling MCP tools directly via JSON-RPC (<code>pods_list</code>, <code>monitorDeployments</code>, <code>getPerformanceMetrics</code>, <code>checkClusterHealth</code>, <code>events_list</code>, <code>resources_list</code>) with AI analysis (Granite/Qwen3 via LiteLLM) and branded HTML email reports via Mailpit</li>
    <li><strong>Workflow auto-import Job</strong> — Helm post-install hook downloads and imports workflow JSON files from <a href="https://github.com/maximilianoPizarro/n8n-sandbox">n8n-sandbox</a></li>
    <li><strong>Mailpit</strong> — Optional SMTP test server with web UI for previewing email reports without external email infrastructure</li>
    <li><strong>Developer Sandbox compatibility</strong> — <code>enableServiceLinks: false</code> to avoid <code>N8N_PORT</code> env conflict, <code>route.sccRoleDisabled</code> for restricted RBAC, empty <code>podSecurityContext</code> for random UID</li>
    <li><strong>Red Hat UBI container image</strong> — Built on <code>registry.access.redhat.com/ubi9/nodejs-22</code>, published at <code>quay.io/maximilianopizarro/n8n</code> via GitHub Actions</li>
    <li><strong>Configurable volume mount path</strong> — <code>main.persistence.mountPath</code> for writable paths in restricted environments</li>
    <li><strong>Chart Verifier CI</strong> — GitHub Actions workflow runs Red Hat Community Helm Chart verification on every push</li>
  </ul>

  <h4 style="color:var(--n8n-blue);margin-top:20px;">Changed</h4>
  <ul>
    <li>Updated n8n app version to <strong>1.123.28</strong></li>
    <li>Dynamic naming in RBAC resources using chart naming helpers</li>
    <li>Architecture diagram updated to Mermaid with MCP Server and AI layer</li>
    <li>GitHub Pages documentation redesigned with n8n-inspired style, lightbox image viewer, and MCP workflow pipeline documentation</li>
  </ul>

  <h4 style="color:var(--n8n-primary);margin-top:20px;">Fixed</h4>
  <ul>
    <li>Fixed <code>ClusterIP_</code> typo in service template</li>
    <li>Fixed hardcoded names in <code>role.yaml</code> to use chart naming helpers (supports <code>n8n-dev-east</code> style release names)</li>
  </ul>

  <h4 style="margin-top:24px;">Email Report Screenshots</h4>
  <p>Actual email reports generated by the MCP workflows and captured in Mailpit:</p>
  <div class="screenshot-grid">
    <div class="screenshot-card">
      <img src="screenshots/mailpit-inbox.png" alt="Mailpit Inbox - 3 workflow email reports">
      <div class="caption">Mailpit Inbox — Resource Quota, Security Audit, Pod Status reports</div>
    </div>
    <div class="screenshot-card">
      <img src="screenshots/mailpit-email-detail.png" alt="Pod Status Report - branded HTML email with pod table">
      <div class="caption">Pod Status Report — Red Hat branded HTML with pod health table, AI analysis by Granite 3.1 8B</div>
    </div>
  </div>

  <h3 style="margin-top:32px;">Upgrade</h3>
  <div class="code-block">helm repo update<br>helm upgrade [RELEASE_NAME] n8n-openshift/n8n --version 1.16.0</div>
  <h3>Uninstall</h3>
  <div class="code-block">helm uninstall [RELEASE_NAME]</div>
</div>

<div class="lightbox-overlay" id="lightbox">
  <span class="lightbox-close" id="lightbox-close">&times;</span>
  <img id="lightbox-img" src="" alt="">
  <div class="lightbox-caption" id="lightbox-caption"></div>
</div>

<script>
(function(){
  var overlay = document.getElementById('lightbox');
  var lbImg = document.getElementById('lightbox-img');
  var lbCap = document.getElementById('lightbox-caption');
  var lbClose = document.getElementById('lightbox-close');

  document.querySelectorAll('.screenshot-card img').forEach(function(img){
    img.addEventListener('click', function(){
      lbImg.src = this.src;
      lbImg.alt = this.alt;
      var caption = this.closest('.screenshot-card').querySelector('.caption');
      lbCap.textContent = caption ? caption.textContent : this.alt;
      overlay.classList.add('active');
      document.body.style.overflow = 'hidden';
    });
  });

  function closeLightbox(){
    overlay.classList.remove('active');
    document.body.style.overflow = '';
  }

  overlay.addEventListener('click', function(e){
    if(e.target === overlay || e.target === lbImg) closeLightbox();
  });
  lbClose.addEventListener('click', closeLightbox);
  document.addEventListener('keydown', function(e){
    if(e.key === 'Escape') closeLightbox();
  });
})();
</script>

<footer class="site-footer">
  <p><strong>n8n Helm Chart</strong> &mdash; Maintained by <a href="https://github.com/maximilianoPizarro">maximilianoPizarro</a></p>
  <p>n8n is licensed under <a href="https://github.com/n8n-io/n8n/blob/master/LICENSE.md">Sustainable Use License</a>. IBM Granite models are licensed under <a href="https://www.apache.org/licenses/LICENSE-2.0">Apache 2.0</a>.</p>
  <p><a href="https://github.com/maximilianoPizarro/n8n-helm-chart">GitHub</a> &bull; <a href="https://artifacthub.io/packages/search?repo=n8n-openshift">Artifact Hub</a> &bull; <a href="https://n8n.io/">n8n.io</a></p>
</footer>
