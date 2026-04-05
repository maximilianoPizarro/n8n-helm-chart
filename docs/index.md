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
    background: var(--n8n-dark);
    color: #a5f3a0;
    padding: 20px;
    border-radius: 12px;
    overflow-x: auto;
    font-family: 'Fira Code', 'Courier New', monospace;
    font-size: 0.85em;
    line-height: 1.4;
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
  }
  .screenshot-card .caption {
    padding: 12px 16px;
    font-size: 0.9em;
    color: var(--n8n-muted);
    background: var(--n8n-light);
    font-weight: 600;
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

<div class="section">
  <h2>Architecture</h2>
  <div class="arch-diagram">
<pre>
┌──────────────┐     ┌────────────────────┐     ┌──────────────────┐     ┌──────────────┐
│   n8n        │────▶│  LiteLLM Proxy     │────▶│  OpenShift MCP   │────▶│  Kubernetes  │
│   Workflow   │     │  + Granite 3.1 8B  │     │  Server          │     │  API         │
│   Engine     │     │  + Qwen 3 8B       │     │  + K8s MCP       │     │              │
└──────┬───────┘     └────────────────────┘     └──────────────────┘     └──────────────┘
       │
       ▼
┌──────────────┐
│  Mailpit     │
│  SMTP/Web UI │
│  (Optional)  │
└──────────────┘
</pre>
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

  <h3>OpenShift MCP Server Workflow Examples</h3>
  <div class="screenshot-grid">
    <div class="screenshot-card">
      <img src="screenshots/n8n-editor-openshift-pod-monitor-ai-agent-mcp-tools.png" alt="Pod Monitor AI Agent with MCP Tools">
      <div class="caption">Pod Monitor - AI Agent with MCP Tools</div>
    </div>
    <div class="screenshot-card">
      <img src="screenshots/n8n-editor-openshift-pod-monitor-mcp-granite-email.png" alt="Pod Monitor MCP + Granite + Email">
      <div class="caption">Pod Monitor - MCP + Granite + Email</div>
    </div>
    <div class="screenshot-card">
      <img src="screenshots/n8n-editor-smtp-test-gmail.png" alt="SMTP Test Workflow">
      <div class="caption">SMTP Test - Email via Mailpit</div>
    </div>
  </div>

  <h3>Dashboard &amp; Services</h3>
  <div class="screenshot-grid">
    <div class="screenshot-card">
      <img src="screenshots/n8n-openshift-mcp-workflow-list.png" alt="n8n Workflow List">
      <div class="caption">n8n Workflow List - OpenShift MCP Workflows</div>
    </div>
    <div class="screenshot-card">
      <img src="screenshots/n8n-dashboard.png" alt="n8n Dashboard">
      <div class="caption">n8n Dashboard Overview</div>
    </div>
    <div class="screenshot-card">
      <img src="screenshots/mailpit-ui.png" alt="Mailpit Web UI">
      <div class="caption">Mailpit - Email Testing Web UI</div>
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
  <p>These workflows query the Kubernetes API through the MCP (Model Context Protocol) server, feed the results to an IBM Granite 3.1 8B model for analysis, and deliver a branded HTML email report via Mailpit.</p>

  <div class="workflow-card">
    <h4>1. Pod Monitor - AI Agent with MCP Tools</h4>
    <p>Queries all pods in the namespace via MCP tools, analyzes status with Granite AI (running, pending, CrashLoopBackOff), and sends an HTML email report with Red Hat branding.</p>
    <div class="meta">
      <span class="tag ai">Granite 3.1 8B</span>
      <span class="tag mcp">OpenShift MCP</span>
      <span class="tag">Manual Trigger</span>
    </div>
  </div>

  <div class="workflow-card">
    <h4>2. Pod Monitor - MCP + Granite + Email</h4>
    <p>Simplified pod monitoring workflow that directly calls the Kubernetes API for pod listing, uses Granite for reasoning, and sends a branded email report.</p>
    <div class="meta">
      <span class="tag ai">Granite 3.1 8B</span>
      <span class="tag mcp">K8s MCP</span>
      <span class="tag">Manual Trigger</span>
    </div>
  </div>

  <div class="workflow-card">
    <h4>3. Deployment Rollout Status</h4>
    <p>Analyzes all Deployments: replica health (desired vs available vs ready), rollout strategy, container image versions, and last rollout conditions. Flags deployments with replica mismatches.</p>
    <div class="meta">
      <span class="tag ai">Granite 3.1 8B</span>
      <span class="tag mcp">K8s MCP</span>
      <span class="tag">Manual Trigger</span>
    </div>
  </div>

  <div class="workflow-card">
    <h4>4. Resource Quota Monitor</h4>
    <p>Scheduled capacity planning: checks ResourceQuota usage, LimitRange configs, aggregate resource consumption, top consumers, and PVC utilization. Flags resources above 80% threshold.</p>
    <div class="meta">
      <span class="tag ai">Granite 3.1 8B</span>
      <span class="tag mcp">OpenShift MCP</span>
      <span class="tag">Schedule (6h)</span>
    </div>
  </div>

  <div class="workflow-card">
    <h4>5. Security Audit</h4>
    <p>Namespace security posture assessment: ServiceAccount roles, privilege escalation, SCC usage, NetworkPolicy, Secrets audit, resource limits enforcement, image registry trust. Findings classified as PASS, WARNING, or CRITICAL.</p>
    <div class="meta">
      <span class="tag ai">Granite 3.1 8B</span>
      <span class="tag mcp">OpenShift MCP</span>
      <span class="tag">Manual Trigger</span>
    </div>
  </div>

  <div class="workflow-card">
    <h4>6. Route &amp; TLS Expiry Check</h4>
    <p>Daily check of all Routes and TLS configuration: termination type, certificate expiry, insecure traffic detection. Alerts on certificates expiring within 30 days.</p>
    <div class="meta">
      <span class="tag ai">Granite 3.1 8B</span>
      <span class="tag mcp">OpenShift MCP</span>
      <span class="tag">Schedule (daily)</span>
    </div>
  </div>

  <div class="workflow-card">
    <h4>7. Event Anomaly Detector</h4>
    <p>Runs every 30 minutes to detect anomalous Kubernetes Events: repeated warnings, OOMKilled, FailedScheduling, image pull errors. Conditional email alerts only when anomalies are found.</p>
    <div class="meta">
      <span class="tag ai">Granite 3.1 8B</span>
      <span class="tag mcp">K8s MCP</span>
      <span class="tag">Schedule (30min)</span>
    </div>
  </div>

  <p>Find all workflow JSON files in the <a href="https://github.com/maximilianoPizarro/n8n-sandbox/tree/main/workflows">n8n-sandbox repository</a>.</p>
</div>

<div class="section">
  <h2>Mailpit Email Output</h2>
  <p>When Mailpit is enabled, n8n workflows can send branded HTML email reports that are captured and viewable in the Mailpit web UI. Configure n8n SMTP credentials to point to the Mailpit service:</p>
  <div class="code-block">main:<br>&nbsp;&nbsp;config:<br>&nbsp;&nbsp;&nbsp;&nbsp;n8n:<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;smtp_host: "&lt;release-name&gt;-mailpit"<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;smtp_port: "1025"<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;smtp_ssl: "false"</div>
  <p>Access the Mailpit web UI via its OpenShift Route to view all captured email reports from your workflows.</p>
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
  <h2>Chart Verification</h2>
  <p>This chart is verified with the Red Hat Community Helm Chart certification process:</p>
  <div class="code-block">podman run --rm -i \<br>&nbsp;&nbsp;-e KUBECONFIG=/.kube/config \<br>&nbsp;&nbsp;-v "$HOME/.kube":/.kube:z \<br>&nbsp;&nbsp;"quay.io/redhat-certification/chart-verifier" \<br>&nbsp;&nbsp;verify --set profile.vendorType=community,profile.version=v1.1 \<br>&nbsp;&nbsp;https://maximilianopizarro.github.io/n8n-helm-chart/n8n-1.16.0.tgz</div>
</div>

<div class="section">
  <h2>Upgrading</h2>
  <h3>Version 1.16.0</h3>
  <p><strong>New Features:</strong></p>
  <ul>
    <li>Mailpit as optional SMTP test service</li>
    <li><code>enableServiceLinks</code> for Developer Sandbox compatibility</li>
    <li>OpenShift MCP Server workflow examples with auto-import</li>
    <li>Dynamic naming in RBAC resources</li>
    <li>Configurable volume mount path (<code>main.persistence.mountPath</code>)</li>
    <li><code>route.sccRoleDisabled</code> for Developer Sandbox RBAC compatibility</li>
    <li>Red Hat UBI-based container image at <code>quay.io/maximilianopizarro/n8n</code></li>
  </ul>
  <h3>Uninstall</h3>
  <div class="code-block">helm uninstall [RELEASE_NAME]</div>
  <h3>Upgrade</h3>
  <div class="code-block">helm upgrade [RELEASE_NAME] n8n-openshift/n8n --version 1.16.0</div>
</div>

<footer class="site-footer">
  <p><strong>n8n Helm Chart</strong> &mdash; Maintained by <a href="https://github.com/maximilianoPizarro">maximilianoPizarro</a></p>
  <p>n8n is licensed under <a href="https://github.com/n8n-io/n8n/blob/master/LICENSE.md">Sustainable Use License</a>. IBM Granite models are licensed under <a href="https://www.apache.org/licenses/LICENSE-2.0">Apache 2.0</a>.</p>
  <p><a href="https://github.com/maximilianoPizarro/n8n-helm-chart">GitHub</a> &bull; <a href="https://artifacthub.io/packages/search?repo=n8n-openshift">Artifact Hub</a> &bull; <a href="https://n8n.io/">n8n.io</a></p>
</footer>
