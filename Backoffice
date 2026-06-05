<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Backoffice Work</title>
    
    <!-- Modern, stable PyScript core framework components -->
    <link rel="stylesheet" href="https://pyscript.net/releases/2024.1.1/core.css" />
    <script type="module" src="https://pyscript.net/releases/2024.1.1/core.js"></script>

    <style>
        :root {
            --primary-color: #3b82f6; /* Electric Blue */
            --primary-hover: #60a5fa;
            --aura-glow: #06b6d4; /* Cyan Accent */
            --bg-gradient: linear-gradient(135deg, #0f172a 0%, #020617 50%, #1e1b4b 100%);
            --card-bg: rgba(30, 41, 59, 0.45); /* Translucent Glass */
            --card-border: rgba(255, 255, 255, 0.08);
            --text-main: #f8fafc;
            --text-muted: #94a3b8;
            --error-bg: rgba(239, 68, 68, 0.15);
            --error-text: #fca5a5;
            --error-border: rgba(239, 68, 68, 0.3);
            --info-bg: rgba(6, 182, 212, 0.1);
            --info-text: #e0f2fe;
            --info-border: rgba(6, 182, 212, 0.3);
            --template-bg: rgba(15, 23, 42, 0.6);
        }

        html, body {
            margin: 0;
            padding: 0;
            width: 100%;
            height: 100%;
            box-sizing: border-box;
        }

        body { 
            font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Helvetica, Arial, sans-serif; 
            background: var(--bg-gradient); 
            background-attachment: fixed;
            color: var(--text-main); 
            display: flex;
            flex-direction: column;
        }

        /* Full Screen Fluid Container */
        .fullscreen-container { 
            flex: 1;
            width: 100%;
            padding: 40px; 
            box-sizing: border-box;
            display: flex;
            flex-direction: column;
            gap: 25px;
        }

        .header-section {
            display: flex;
            align-items: center;
            justify-content: space-between;
            background: var(--card-bg);
            backdrop-filter: blur(12px);
            -webkit-backdrop-filter: blur(12px);
            padding: 24px 40px;
            border-radius: 16px;
            box-shadow: 0 8px 32px 0 rgba(0, 0, 0, 0.3);
            border: 1px solid var(--card-border);
        }

        .brand-title-group {
            display: flex;
            align-items: center;
            gap: 20px;
        }

        /* Customized Premium Samsung Style Badge */
        .samsung-badge {
            background-color: #ffffff;
            color: #000000;
            font-family: "Segoe UI", Black, sans-serif;
            font-weight: 900;
            font-size: 14px;
            letter-spacing: 3px;
            padding: 10px 20px;
            border-radius: 6px;
            text-transform: uppercase;
            box-shadow: 0 0 20px rgba(255, 255, 255, 0.15);
        }

        h2 { 
            margin: 0; 
            color: var(--text-main); 
            font-size: 28px;
            font-weight: 700;
            letter-spacing: -0.5px;
        }

        .subtitle { 
            color: var(--text-muted); 
            font-size: 14px;
            margin: 4px 0 0 0;
        }

        /* Control Center Panel (Dropdowns + Search) */
        .control-panel {
            background: var(--card-bg);
            backdrop-filter: blur(12px);
            -webkit-backdrop-filter: blur(12px);
            padding: 30px 40px;
            border-radius: 16px;
            box-shadow: 0 8px 32px 0 rgba(0, 0, 0, 0.3);
            border: 1px solid var(--card-border);
            display: flex;
            flex-direction: column;
            gap: 20px;
        }

        .selectors-row {
            display: flex;
            gap: 20px;
            flex-wrap: wrap;
        }

        .dropdown-group {
            display: flex;
            flex-direction: column;
            gap: 8px;
            min-width: 280px;
        }

        /* Hidden class for dynamic component toggle */
        .hidden {
            display: none !important;
        }

        .control-label {
            font-size: 13px;
            font-weight: 600;
            text-transform: uppercase;
            letter-spacing: 1px;
            color: var(--aura-glow);
        }

        select {
            padding: 14px 16px;
            border: 1px solid var(--card-border);
            border-radius: 10px;
            font-size: 16px;
            color: var(--text-main);
            background-color: rgba(15, 23, 42, 0.8);
            outline: none;
            cursor: pointer;
            transition: all 0.3s ease;
        }

        select:focus {
            border-color: var(--primary-color);
            box-shadow: 0 0 15px rgba(59, 130, 246, 0.3);
        }

        select option {
            background-color: #0f172a;
            color: var(--text-main);
        }

        .search-row {
            display: flex;
            gap: 16px;
        }

        input { 
            flex: 1;
            padding: 16px 20px; 
            box-sizing: border-box; 
            border: 1px solid var(--card-border); 
            border-radius: 10px; 
            font-size: 16px; 
            transition: all 0.3s ease;
            outline: none;
            color: var(--text-main);
            background-color: rgba(15, 23, 42, 0.6);
        }

        input:focus {
            background-color: rgba(15, 23, 42, 0.8);
            border-color: var(--primary-color);
            box-shadow: 0 0 15px rgba(59, 130, 246, 0.3);
        }

        button { 
            padding: 0 40px;
            background: linear-gradient(135deg, var(--primary-color) 0%, #1d4ed8 100%);
            color: white; 
            border: none; 
            border-radius: 10px; 
            font-size: 16px; 
            cursor: pointer; 
            font-weight: 600; 
            transition: all 0.3s ease;
            white-space: nowrap;
            box-shadow: 0 4px 14px rgba(59, 130, 246, 0.4);
        }

        button:hover { 
            background: linear-gradient(135deg, var(--primary-hover) 0%, #2563eb 100%);
            box-shadow: 0 4px 20px rgba(6, 182, 212, 0.4);
            transform: translateY(-1px);
        }

        button:active {
            transform: scale(0.99);
        }

        /* Full space grid area for matching results */
        .results-workspace {
            flex: 1;
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(450px, 1fr));
            gap: 24px;
            align-content: start;
        }

        .message-banner { 
            grid-column: 1 / -1;
            font-weight: 500; 
            padding: 18px 24px; 
            border-radius: 12px; 
            font-size: 16px;
            backdrop-filter: blur(4px);
        }

        .error {
            color: var(--error-text); 
            background: var(--error-bg); 
            border: 1px solid var(--error-border); 
        }

        /* Premium Radiant Result Cards */
        .result-card { 
            padding: 26px; 
            border: 1px solid var(--card-border);
            background: var(--card-bg); 
            backdrop-filter: blur(8px);
            -webkit-backdrop-filter: blur(8px);
            border-radius: 16px; 
            box-shadow: 0 4px 20px rgba(0,0,0,0.15); 
            transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
            display: flex;
            flex-direction: column;
            justify-content: start;
            position: relative;
            overflow: hidden;
        }

        .result-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(235deg, transparent, rgba(6, 182, 212, 0.05));
            pointer-events: none;
        }

        .result-card:hover {
            transform: translateY(-2px);
            box-shadow: 0 12px 30px rgba(6, 182, 212, 0.15);
            border-color: rgba(6, 182, 212, 0.3);
        }

        .result-card h3 { 
            margin: 0 0 18px 0; 
            color: #ffffff; 
            font-size: 21px;
            font-weight: 600;
            border-bottom: 1px solid rgba(255, 255, 255, 0.08);
            padding-bottom: 12px;
            letter-spacing: -0.3px;
        }

        .contact-row {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin: 10px 0;
            font-size: 15px;
        }

        .contact-label {
            font-weight: 500;
            color: var(--text-muted);
        }

        .contact-value a {
            color: var(--primary-hover);
            text-decoration: none;
            font-weight: 500;
            transition: color 0.2s ease, text-shadow 0.2s ease;
        }

        .contact-value a:hover {
            color: var(--aura-glow);
            text-shadow: 0 0 8px rgba(6, 182, 212, 0.6);
            text-decoration: underline;
        }

        .contact-value .missing {
            color: rgba(148, 163, 184, 0.4);
            font-style: italic;
        }

        /* Embedded Email Template Section Styles */
        .template-box {
            margin-top: 20px;
            padding: 16px;
            background-color: var(--template-bg);
            border: 1px dashed rgba(6, 182, 212, 0.3);
            border-radius: 10px;
            font-size: 14px;
        }

        .template-header {
            font-size: 12px;
            font-weight: bold;
            color: var(--aura-glow);
            text-transform: uppercase;
            letter-spacing: 0.5px;
            margin-bottom: 10px;
            display: flex;
            align-items: center;
            gap: 6px;
        }

        .template-field {
            margin-bottom: 8px;
            border-bottom: 1px solid rgba(255, 255, 255, 0.05);
            padding-bottom: 6px;
        }

        .template-field:last-child {
            border-bottom: none;
            padding-bottom: 0;
            margin-bottom: 0;
        }

        .field-label {
            font-weight: 600;
            color: var(--text-muted);
            margin-right: 5px;
        }

        .field-body-text {
            display: block;
            margin-top: 6px;
            color: #e2e8f0;
            white-space: pre-line;
            line-height: 1.5;
            background: rgba(0, 0, 0, 0.2);
            padding: 10px;
            border-radius: 6px;
        }
    </style>
</head>
<body>

<div class="fullscreen-container">
    <!-- Header Panel -->
    <div class="header-section">
        <div class="brand-title-group">
            <div class="samsung-badge">Samsung</div>
            <div>
                <h2>Backoffice Work</h2>
                <p class="subtitle">Search live routing channels, operations management, and parcel systems.</p>
            </div>
        </div>
    </div>
    
    <!-- Control Panel -->
    <div class="control-panel">
        <div class="selectors-row">
            <!-- Dropdown Selector Group 1 -->
            <div class="dropdown-group">
                <label class="control-label" for="issue-select">Select Issue Context</label>
                <select id="issue-select" py-change="toggle_issue_context">
                    <option value="bopis">BOPIS (Buy Online, Pick Up In Store)</option>
                    <option value="courier">Courier Routing</option>
                </select>
            </div>

            <!-- Dropdown Selector Group 2 (Shows up for Couriers) -->
            <div class="dropdown-group hidden" id="courier-dropdown-wrapper">
                <label class="control-label" for="courier-select">Select Logistics Provider</label>
                <select id="courier-select">
                    <option value="all">-- All Couriers --</option>
                    <option value="BRING Logistics">BRING</option>
                    <option value="Postnord Distribution">PostNord</option>
                    <option value="Posti Group">Posti</option>
                    <option value="Skanlog Supply Chain">Skanlog</option>
                </select>
            </div>
        </div>

        <!-- Dynamic Action Row -->
        <div class="search-row">
            <input type="text" id="store-input" placeholder="Type store name to search (e.g. Vinterbro, Porvoo)...">
            <button id="search-btn" py-click="execute_search">Search Data Channel</button>
        </div>
    </div>

    <!-- Wide Screen Results Target -->
    <div id="output" class="results-workspace"></div>
</div>

<script type="py">
from pyscript import document

# BOPIS Store Database Configuration
BOPIS_DATABASE = {
    "Elkjøp Arendal": {"ops": "dm.operations.arendal@elkjop.no", "mgr": "storemanager.arendal@elkjop.no"},
    "Elkjøp Gullgruven Åsane": {"ops": "dm.operations.gullgruven@elkjop.no", "mgr": "storemanager.gullgruven@elkjop.no"},
    "Elkjøp Bodø": {"ops": "dm.operations.bodo@elkjop.no", "mgr": "storemanager.bodo@elkjop.no"},
    "Elkjøp Fredrikstad": {"ops": "dm.operations.fredrikstad@elkjop.no", "mgr": "storemanager.fredrikstad@elkjop.no"},
    "Elkjøp Gjøvik": {"ops": "dm.operations.gjovik@elkjop.no", "mgr": "storemanager.gjovik@elkjop.no"},
    "Elkjøp Hamar": {"ops": "dm.operations.hamar@elkjop.no", "mgr": "storemanager.hamar@elkjop.no"},
    "Elkjøp Tønsberg": {"ops": "dm.operations.tonsberg@elkjop.no", "mgr": "storemanager.tonsberg@elkjop.no"},
    "Elkjøp Halden": {"ops": "dm.operations.halden@elkjop.no", "mgr": "storemanager.halden@elkjop.no"},
    "Elkjøp Sartor": {"ops": "dm.operations.sartor@elkjop.no", "mgr": "storemanager.sartor@elkjop.no"},
    "Elkjøp Kristiansand": {"ops": "dm.operations.kristiansand@elkjop.no", "mgr": "storemanager.kristiansand@elkjop.no"},
    "Elkjøp Lillehammer": {"ops": "dm.operations.lillehammer@elkjop.no", "mgr": "storemanager.lillehammer@elkjop.no"},
    "Elkjøp Lørenskog": {"ops": "dm.operations.lorenskog@elkjop.no", "mgr": "storemanager.lorenskog@elkjop.no"},
    "Elkjøp Slependen": {"ops": "dm.operations.slependen@elkjop.no", "mgr": "storemanager.slependen@elkjop.no"},
    "Elkjøp Vinterbro": {"ops": "dm.operations.vinterbro@elkjop.no", "mgr": "storemanager.vinterbro@elkjop.no"},
    "Elkjøp Skien": {"ops": "dm.operations.skien@elkjop.no", "mgr": "storemanager.skien@elkjop.no"},
    "Elkjøp Tromsø": {"ops": "dm.operations.tromso@elkjop.no", "mgr": "storemanager.tromso@elkjop.no"},
    "Elkjøp Tillertorget": {"ops": "dm.operations.tillertorget@elkjop.no", "mgr": "storemanager.tillertorget@elkjop.no"},
    "Elkjøp Ullevål": {"ops": "dm.operations.ulleval@elkjop.no", "mgr": "storemanager.ulleval@elkjop.no"},
    "Elkjøp Fana": {"ops": "dm.operations.fana@elkjop.no", "mgr": "storemanager.fana@elkjop.no"},
    "Elkjøp Forus": {"ops": "dm.operations.forus@elkjop.no", "mgr": "storemanager.forus@elkjop.no"},
    "Elkjøp Kleppe": {"ops": "dm.operations.kleppe@elkjop.no", "mgr": "storemanager.kleppe@elkjop.no"},
    "Elkjøp Sarpsborg": {"ops": "dm.operations.sarpsborg@elkjop.no", "mgr": "storemanager.sarpsborg@elkjop.no"},
    "Elkjøp Sandefjord": {"ops": "dm.operations.sandefjord@elkjop.no", "mgr": "storemanager.sandefjord@elkjop.no"},
    "Elkjøp Larvik": {"ops": "dm.operations.larvik@elkjop.no", "mgr": "storemanager.larvik@elkjop.no"},
    "Elkjøp Harstad": {"ops": "dm.operations.harstad@elkjop.no", "mgr": "storemanager.harstad@elkjop.no"},
    "Elkjøp Haugesund": {"ops": "dm.operations.haugesund@elkjop.no", "mgr": "storemanager.haugesund@elkjop.no"},
    "Elkjøp Jessheim": {"ops": "dm.operations.jessheim@elkjop.no", "mgr": "storemanager.jessheim@elkjop.no"},
    "Elkjøp Skøyen": {"ops": "dm.operations.skoyen@elkjop.no", "mgr": "storemanager.skoyen@elkjop.no"},
    "Elkjøp Lade": {"ops": "dm.operations.lade@elkjop.no", "mgr": "storemanager.lade@elkjop.no"},
    "Elkjøp Porsgrunn": {"ops": "dm.operations.porsgrunn@elkjop.no", "mgr": "storemanager.porsgrunn@elkjop.no"},
    "Elkjøp Kristiansund": {"ops": "dm.operations.kristiansand@elkjop.no", "mgr": "storemanager.kristiansund@elkjop.no"},
    "Elkjøp Kongsvinger": {"ops": "dm.operations.kongsvinger@elkjop.no", "mgr": "storemanager.kongsvinger@elkjop.no"},
    "Elkjøp Drammen": {"ops": "dm.operations.drammen@elkjop.no", "mgr": "storemanager.drammen@elkjop.no"},
    "Elkjøp Buskerud": {"ops": "dm.operations.buskerud@elkjop.no", "mgr": "storemanager.buskerud@elkjop.no"},
    "Elkjøp Kongsberg": {"ops": "dm.operations.kongsberg@elkjop.no", "mgr": "storemanager.kongsberg@elkjop.no"},
    "Elkjøp Glasmagasinet": {"ops": "dm.operations.glasmagasinet@elkjop.no", "mgr": "storemanager.glasmagasinet@elkjop.no"},
    "Elkjøp Ski": {"ops": "dm.operations.ski@elkjop.no", "mgr": "storemanager.ski@elkjop.no"},
    "Elkjøp Åkrehamn": {"ops": "dm.operations.akra@elkjop.no", "mgr": "storemanager.akra@elkjop.no"},
    "Elkjøp Alta": {"ops": "dm.operations.alta@elkjop.no", "mgr": "storemanager.alta@elkjop.no"},
    "Elkjøp Årnes": {"ops": "dm.operations.arnes@elkjop.no", "mgr": "storemanager.arnes@elkjop.no"},
    "Elkjøp Dokka": {"ops": "dm.operations.dokka@elkjop.no", "mgr": "storemanager.dokka@elkjop.no"},
    "Elkjøp Dombås": {"ops": "dm.operations.dombas@elkjop.no", "mgr": "storemanager.dombas@elkjop.no"},
    "Elkjøp Elverum": {"ops": "dm.operations.elverum@elkjop.no", "mgr": "storemanager.elverum@elkjop.no"},
    "Elkjøp Valdres": {"ops": "dm.operations.valdres@elkjop.no", "mgr": "storemanager.valdres@elkjop.no"},
    "Elkjøp Florø": {"ops": "dm.operations.floro@elkjop.no", "mgr": "storemanager.floro@elkjop.no"},
    "Elkjøp Hadeland": {"ops": "dm.operations.hadeland@elkjop.no", "mgr": "storemanager.hadeland@elkjop.no"},
    "Elkjøp Hønefoss": {"ops": "dm.operations.honefoss@elkjop.no", "mgr": "storemanager.honefoss@elkjop.no"},
    "Elkjøp Leknes": {"ops": "dm.operations.leknes@elkjop.no", "mgr": "storemanager.leknes@elkjop.no"},
    "Elkjøp Svolvær": {"ops": "dm.operations.svolvaer@elkjop.no", "mgr": "storemanager.svolvaer@elkjop.no"},
    "Elkjøp Oppdal": {"ops": "dm.operations.oppdal@elkjop.no", "mgr": "storemanager.oppdal@elkjop.no"},
    "Elkjøp Lyngdal": {"ops": "dm.operations.lyngdal@elkjop.no", "mgr": "storemanager.lyngdal@elkjop.no"},
    "Elkjøp Moss": {"ops": "dm.operations.moss@elkjop.no", "mgr": "storemanager.moss@elkjop.no"},
    "Elkjøp Narvik": {"ops": "dm.operations.narvik@elkjop.no", "mgr": "storemanager.narvik@elkjop.no"},
    "Elkjøp Sunndal": {"ops": "dm.operations.sunndal@elkjop.no", "mgr": "storemanager.sunndal@elkjop.no"},
    "Elkjøp Namsos": {"ops": "dm.operations.namsos@elkjop.no", "mgr": "storemanager.namsos@elkjop.no"},
    "Elkjøp Tinn": {"ops": "dm.operations.tinn@elkjop.no", "mgr": "storemanager.tinn@elkjop.no"},
    "Elkjøp Levanger": {"ops": "dm.operations.levanger@elkjop.no", "mgr": "storemanager.levanger@elkjop.no"},
    "Elkjøp Steinkjer": {"ops": "dm.operations.steinkjer@elkjop.no", "mgr": "storemanager.steinkjer@elkjop.no"},
    "Elkjøp Stokmarknes": {"ops": "dm.operations.stokmarknes@elkjop.no", "mgr": "storemanager.stokmarknes@elkjop.no"},
    "Elkjøp Os": {"ops": "dm.operations.os@elkjop.no", "mgr": "storemanager.os@elkjop.no"},
    "Elkjøp Sortland": {"ops": "dm.operations.sortland@elkjop.no", "mgr": "storemanager.sortland@elkjop.no"},
    "Elkjøp Orkanger": {"ops": "dm.operations.orkanger@elkjop.no", "mgr": "storemanager.orkanger@elkjop.no"},
    "Elkjøp Vinje": {"ops": "dm.operations.vinje@elkjop.no", "mgr": "storemanager.vinje@elkjop.no"},
    "Elkjøp Otta": {"ops": "dm.operations.otta@elkjop.no", "mgr": "storemanager.otta@elkjop.no"},
    "Elkjøp Stjørdal": {"ops": "dm.operations.stjordal@elkjop.no", "mgr": "storemanager.stjordal@elkjop.no"},
    "Elkjøp Støren": {"ops": "dm.operations.storen@elkjop.no", "mgr": "storemanager.storen@elkjop.no"},
    "Elkjøp Sogn": {"ops": "dm.operations.sogn@elkjop.no", "mgr": "storemanager.sogn@elkjop.no"},
    "Elkjøp Førde": {"ops": "dm.operations.forde@elkjop.no", "mgr": "storemanager.forde@elkjop.no"},
    "Elkjøp Måløy": {"ops": "dm.operations.maloy@elkjop.no", "mgr": "storemanager.maloy@elkjop.no"},
    "Elkjøp Hammerfest": {"ops": "dm.operations.hammerfest@elkjop.no", "mgr": "storemanager.hammerfest@elkjop.no"},
    "Elkjøp Askøy": {"ops": "dm.operations.askoy@elkjop.no", "mgr": "storemanager.askoy@elkjop.no"},
    "Elkjøp Verdal": {"ops": "dm.operations.verdal@elkjop.no", "mgr": "storemanager.verdal@elkjop.no"},
    "Elkjøp Stavanger Sentrum": {"ops": "dm.operations.stavanger@elkjop.no", "mgr": "storemanager.stavanger@elkjop.no"},
    "Elkjøp Horten": {"ops": "dm.operations.horten@elkjop.no", "mgr": "storemanager.horten@elkjop.no"},
    "Elkjøp Gol": {"ops": "dm.operations.gol@elkjop.no", "mgr": "storemanager.gol@elkjop.no"},
    "Elkjøp Husnes": {"ops": "dm.operations.husnes@elkjop.no", "mgr": "storemanager.husnes@elkjop.no"},
    "Elkjøp Ulsteinvik Blåhuset": {"ops": "dm.operations.blahuset@elkjop.no", "mgr": "storemanager.blahuset@elkjop.no"},
    "Elkjøp Bømlo": {"ops": "dm.operations.bomlo@elkjop.no", "mgr": "storemanager.bomlo@elkjop.no"},
    "Elkjøp Ørsta": {"ops": "dm.operations.orsta@elkjop.no", "mgr": "storemanager.orsta@elkjop.no"},
    "Elkjøp Egersund": {"ops": "dm.operations.egersund@elkjop.no", "mgr": "storemanager.egersund@elkjop.no"},
    "Elkjøp Stord": {"ops": "dm.operations.stord@elkjop.no", "mgr": "storemanager.stord@elkjop.no"},
    "Elkjøp Ål": {"ops": "dm.operations.al@elkjop.no", "mgr": "storemanager.al@elkjop.no"},
    "Elkjøp Fauske": {"ops": "dm.operations.fauske@elkjop.no", "mgr": "storemanager.fauske@elkjop.no"},
    "Elkjøp Nittedal": {"ops": "dm.operations.nittedal@elkjop.no", "mgr": "storemanager.nittedal@elkjop.no"},
    "Elkjøp Mosjøen": {"ops": "dm.operations.mosjoen@elkjop.no", "mgr": "storemanager.mosjoen@elkjop.no"},
    "Elkjøp Mo i Rana": {"ops": "dm.operations.mo@elkjop.no", "mgr": "storemanager.mo@elkjop.no"},
    "Elkjøp Fosen": {"ops": "dm.operations.fosen@elkjop.no", "mgr": "storemanager.fosen@elkjop.no"},
    "Elkjøp Flekkefjord": {"ops": "dm.operations.flekkefjord@elkjop.no", "mgr": "storemanager.flekkefjord@elkjop.no"},
    "Elkjøp Tvedestrand": {"ops": "dm.operations.tvedestrand@elkjop.no", "mgr": "storemanager.tvedestrand@elkjop.no"},
    "Elkjøp Fyllingsdalen": {"ops": "dm.operations.fyllingsdalen@elkjop.no", "mgr": "storemanager.fyllingsdalen@elkjop.no"},
    "Elkjøp Kirkenes": {"ops": "dm.operations.kirkenes@elkjop.no", "mgr": "storemanager.kirkenes@elkjop.no"},
    "Elkjøp Voss": {"ops": "dm.operations.voss@elkjop.no", "mgr": "storemanager.voss@elkjop.no"},
    "Elkjøp Gloppen": {"ops": "dm.operations.gloppen@elkjop.no", "mgr": "storemanager.gloppen@elkjop.no"},
    "Elkjøp Ålesund Moa": {"ops": "dm.operations.moa@elkjop.no", "mgr": "storemanager.moa@elkjop.no"},
    "Elkjøp Rudshøgda": {"ops": "dm.operations.rudshogda@elkjop.no", "mgr": "storemanager.rudshogda@elkjop.no"},
    "Elkjøp Molde": {"ops": "dm.operations.molde@elkjop.no", "mgr": "storemanager.molde@elkjop.no"},
    "Elkjøp Finnsnes": {"ops": "dm.operations.finnsnes@elkjop.no", "mgr": "storemanager.finnsnes@elkjop.no"},
    "Elkjøp Notodden": {"ops": "dm.operations.notodden@elkjop.no", "mgr": "storemanager.notodden@elkjop.no"},
    "Elkjøp Ulsteinvik Saunesmarka": {"ops": "dm.operations.ulsteinvik@elkjop.no", "mgr": "storemanager.ulsteinvik@elkjop.no"},
    "Elkjøp Volda": {"ops": "dm.operations.volda@elkjop.no", "mgr": "storemanager.volda@elkjop.no"},
    "Elkjøp Ålesund Breivika": {"ops": "dm.operations.breivika@elkjop.no", "mgr": "storemanager.breivika@elkjop.no"},
    "Elkjøp Sandvika": {"ops": "dm.operations.sandvika@elkjop.no", "mgr": "storemanager.sandvika@elkjop.no"},
    "Elkjøp Strømmen": {"ops": "dm.operations.strommen@elkjop.no", "mgr": "storemanager.strommen@elkjop.no"},
    "Elkjøp Alna": {"ops": "dm.operations.alna@elkjop.no", "mgr": "storemanager.alna@elkjop.no"},
    "Elkjøp Nordre Gate": {"ops": "dm.operations.nordregate@elkjop.no", "mgr": "storemanager.nordregate@elkjop.no"},
    "Elkjøp Sandnes": {"ops": "dm.operations.sandnes@elkjop.no", "mgr": "storemanager.sandnes@elkjop.no"},
    "Elkjøp Lagunen": {"ops": "dm.operations.lagunen@elkjop.no", "mgr": "storemanager.lagunen@elkjop.no"},
    "Elkjøp Østfoldhallene": {"ops": "dm.operations.dikeveien@elkjop.no", "mgr": "storemanager.dikeveien@elkjop.no"},
    "Elkjøp Åsane Storsenter": {"ops": "dm.operations.asane@elkjop.no", "mgr": "storemanager.asane@elkjop.no"},
    "Elkjøp Gulskogen": {"ops": "dm.operations.gulskogen@elkjop.no", "mgr": "storemanager.gulskogen@elkjop.no"},
    "Elkjøp Vikingskipet": {"ops": "dm.operations.vikingskipet@elkjop.no", "mgr": "storemanager.vikingskipet@elkjop.no"},
    "Elkjøp Sørlandssenteret": {"ops": "dm.operations.sorlandssenteret@elkjop.no", "mgr": "storemanager.sorlandssenteret@elkjop.no"},
    "Elkjøp Haugesund Bergsenteret": {"ops": "dm.operations.bergsenteret@elkjop.no", "mgr": "storemanager.bergsenteret@elkjop.no"},
    "Elkjøp Molde Storsenter": {"ops": "dm.operations.moldestorsenter@elkjop.no", "mgr": "storemanager.moldestorsenter@elkjop.no"},
    "Elkjøp Kjørbekk": {"ops": "dm.operations.kjorbekk@elkjop.no", "mgr": "storemanager.kjorbekk@elkjop.no"},
    "Elkjøp Storo": {"ops": "dm.operations.storo@elkjop.no", "mgr": "storemanager.storo@elkjop.no"},
    "Elkjøp Langnes": {"ops": "dm.operations.langnes@elkjop.no", "mgr": "storemanager.langnes@elkjop.no"},
    "Gigantti Porvoo": {"ops": "dm.operations.porvoo@gigantti.fi", "mgr": "storemanager.porvoo@gigantti.fi"},
    "Gigantti Riihimäki": {"ops": "dm.operations.riihimaki@gigantti.fi", "mgr": "storemanager.riihimaki@gigantti.fi"},
    "Gigantti Iisalmi": {"ops": "dm.operations.iisalmi@gigantti.fi", "mgr": "storemanager.iisalmi@gigantti.fi"},
    "Gigantti Huittinen": {"ops": "dm.operations.huittinen@gigantti.fi", "mgr": "storemanager.huittinen@gigantti.fi"},
    "Gigantti Salon Kodintekniikka Oy": {"ops": "dm.operations.salo@gigantti.fi", "mgr": "storemanager.salo@gigantti.fi"}
}

# Courier Logistic Directory Configuration
COURIER_DATABASE = {
    "BRING Logistics": {"ops": "bring.nordic.ops@bring.com", "mgr": "bring.accountmanagement@bring.com"},
    "Postnord Distribution": {"ops": "postnord.fulfillment.support@postnord.com", "mgr": "postnord.transport.mgr@postnord.com"},
    "Posti Group": {"ops": "posti.fi.operations@posti.com", "mgr": "posti.business.solutions@posti.com"},
    "Skanlog Supply Chain": {"ops": "skanlog.controltower@skanlog.com", "mgr": "skanlog.accountdirector@skanlog.com"}
}

def toggle_issue_context(event):
    """Manages visibility of controls based on selected operations mode and resets workspace."""
    selected_issue = document.getElementById("issue-select").value
    courier_wrapper = document.getElementById("courier-dropdown-wrapper")
    text_input = document.getElementById("store-input")
    output_div = document.getElementById("output")
    
    # Force reset the layout output workspace immediately when changing context tabs
    output_div.innerHTML = ""
    
    if selected_issue == "courier":
        courier_wrapper.classList.remove("hidden")
        text_input.classList.add("hidden")  # Hide input, text searches completely blocked
    else:
        courier_wrapper.classList.add("hidden")
        text_input.classList.remove("hidden") # Show text input for store data search

def execute_search(event):
    output_div = document.getElementById("output")
    selected_issue = document.getElementById("issue-select").value
    selected_courier = document.getElementById("courier-select").value
    search_query = document.getElementById("store-input").value.strip().lower()
    
    html_results = ""

    # --- MODE 1: COURIER ROUTING ENGINE (Purely Dropdown Driven - No Template Box) ---
    if selected_issue == "courier":
        for courier_name, data in COURIER_DATABASE.items():
            if (selected_courier == "all") or (selected_courier == courier_name):
                op_mail = f'<a href="mailto:{data["ops"]}">{data["ops"]}</a>' if data["ops"] else '<span class="missing">Not Listed</span>'
                sm_mail = f'<a href="mailto:{data["mgr"]}">{data["mgr"]}</a>' if data["mgr"] else '<span class="missing">Not Listed</span>'
                
                html_results += f"""
                <div class="result-card">
                    <h3>🚚 {courier_name}</h3>
                    <div class="contact-row">
                        <span class="contact-label">Logistics Operations</span>
                        <span class="contact-value">{op_mail}</span>
                    </div>
                    <div class="contact-row">
                        <span class="contact-label">Key Account Manager</span>
                        <span class="contact-value">{sm_mail}</span>
                    </div>
                </div>
                """
        output_div.innerHTML = html_results

    # --- MODE 2: BOPIS STORE ROUTING ENGINE (With Integrated Custom Template Output) ---
    else:
        if not search_query:
            output_div.innerHTML = '<div class="message-banner error">⚠️ Please type a store name before executing a BOPIS search.</div>'
            return

        for store_name, data in BOPIS_DATABASE.items():
            if search_query in store_name.lower():
                ops_email = data["ops"]
                mgr_email = data["mgr"]
                
                op_mail_link = f'<a href="mailto:{ops_email}">{ops_email}</a>' if ops_email else '<span class="missing">Not Listed</span>'
                sm_mail_link = f'<a href="mailto:{mgr_email}">{mgr_email}</a>' if mgr_email else '<span class="missing">Not Listed</span>'
                
                # Dynamic construction of custom requested email layout template block
                html_results += f"""
                <div class="result-card">
                    <h3>🏬 {store_name}</h3>
                    <div class="contact-row">
                        <span class="contact-label">Operations Manager</span>
                        <span class="contact-value">{op_mail_link}</span>
                    </div>
                    <div class="contact-row">
                        <span class="contact-label">Store Manager</span>
                        <span class="contact-value">{sm_mail_link}</span>
                    </div>
                    
                    <!-- Appended Copyable Email Notification Template Block -->
                    <div class="template-box">
                        <div class="template-header">📧 Notification Template</div>
                        <div class="template-field">
                            <span class="field-label">To:</span> {ops_email}; {mgr_email}
                        </div>
                        <div class="template-field">
                            <span class="field-label">Subject:</span> 
                        </div>
                        <div class="template-field">
                            <span class="field-label">Body Blueprint:</span>
                            <span class="field-body-text">Hi,
Describe the issue
Product 1: SM-S931BZSGEUB / Galaxy S25
Product 2: EF-VS931PJEGWW / Galaxy S25 Kindsuit Case
Elkjöp SO number: 20xxxxx
Samsung PO number: SE250608-xxxxxx
BP: 25xxxxx
Store: {store_name}</span>
                        </div>
                    </div>
                </div>
                """
                
        if not html_results:
            output_div.innerHTML = f'<div class="message-banner error">🔍 No BOPIS configurations active matching "{search_query}".</div>'
        else:
            output_div.innerHTML = html_results
</script>

</body>
</html>
