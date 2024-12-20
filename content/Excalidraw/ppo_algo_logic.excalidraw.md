---

excalidraw-plugin: parsed
tags: [excalidraw]

---
==⚠  Switch to EXCALIDRAW VIEW in the MORE OPTIONS menu of this document. ⚠==


# Text Elements
Start Script ^PfsUKXRS

Parse Arguments ^2Ed5u2mJ

Environment Setup ^8pdjjqPb

Initialize Agent and Optimizer ^e0TIxuPV

Training Loop ^EGvGDVrf

Evaluate During Training ^dv047gln

Log Metrics ^bjhqWcfk

Optional: Save Model ^BAwiAj9Y

Optional: Evaluate Saved Model ^0iLjJURD

Optional: Upload Model ^1hzNbigD

Start Training Loop ^eKFqP4Kw

Iterate Over Timesteps ^Ptl3HE4f

Collect Rollouts ^ldOVN9kO

Store Observations, Actions, Rewards, Values, Log-Probs ^0bpzDQi3

Compute GAE and Returns ^azpemZa9

Iterate Over Epochs ^UIDHOeih

Batch Sampling ^V0K5tJqR

Calculate PPO Loss ^M0vDxDu4

Surrogate Objective Loss ^6082HVHf

Value Function Loss ^kYqIhnjh

Entropy Bonus ^zwh8iX14

Backpropagation and Optimization ^aGlIliht

Update Policy and Value Networks ^c78FNmqm

Optional: Update Learning Rate ^z0SjWW4w

End Epoch ^PriIFxEU

Log Training Metrics ^SLJtAijU

Save Rollouts for Debugging ^u6VFifcz

End Timestep ^qG91oNxf

Training logic ^SDULvO24

%%
# Drawing
```json
{
	"type": "excalidraw",
	"version": 2,
	"source": "https://github.com/zsviczian/obsidian-excalidraw-plugin/releases/tag/2.0.10",
	"elements": [
		{
			"type": "rectangle",
			"version": 521,
			"versionNonce": 2112356670,
			"isDeleted": false,
			"id": "aUlOqw6KqPhKn5pyLm710",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -236.44227101249112,
			"y": -1613.5600727587075,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 233.9038375053764,
			"height": 81.49612731328487,
			"seed": 1143031266,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"type": "text",
					"id": "PfsUKXRS"
				},
				{
					"id": "ef6Ulq4ErI8SXKoZx4Gxd",
					"type": "arrow"
				}
			],
			"updated": 1734617956032,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 522,
			"versionNonce": 101788030,
			"isDeleted": false,
			"id": "l0uf5VxRwFAmYXFUxCq9a",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -283.2410133391511,
			"y": -1439.4547098621445,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 327.50132215869695,
			"height": 81.49612731328487,
			"seed": 897726882,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"type": "text",
					"id": "2Ed5u2mJ"
				},
				{
					"id": "DCAwl2Qrh3bD6bklZdrlc",
					"type": "arrow"
				},
				{
					"id": "ef6Ulq4ErI8SXKoZx4Gxd",
					"type": "arrow"
				}
			],
			"updated": 1734617956032,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 520,
			"versionNonce": 929778110,
			"isDeleted": false,
			"id": "z3t7c4c_hiRxXmrqyuY0w",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -305.9149718985152,
			"y": -1265.3493469655812,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 372.8492392774251,
			"height": 81.49612731328487,
			"seed": 2114893154,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"type": "text",
					"id": "8pdjjqPb"
				},
				{
					"id": "DCAwl2Qrh3bD6bklZdrlc",
					"type": "arrow"
				},
				{
					"id": "yVeSmkSnX0zihdiCSJPK5",
					"type": "arrow"
				}
			],
			"updated": 1734617956032,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 520,
			"versionNonce": 823615998,
			"isDeleted": false,
			"id": "TowUw9AuAjQS56vuzlRmv",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -407.31866652017857,
			"y": -1091.243984069018,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 575.6566285207518,
			"height": 81.49612731328487,
			"seed": 1058388258,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"type": "text",
					"id": "e0TIxuPV"
				},
				{
					"id": "yVeSmkSnX0zihdiCSJPK5",
					"type": "arrow"
				},
				{
					"id": "1eEJpS12-ke5fXYPxpo0I",
					"type": "arrow"
				}
			],
			"updated": 1734617956032,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 525,
			"versionNonce": 17442594,
			"isDeleted": false,
			"id": "zPQ7qWK58sMJXgQMOaz_F",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -254.8279497537194,
			"y": -917.1386211724549,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 270.6751949878332,
			"height": 81.49612731328487,
			"seed": 403064034,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"type": "text",
					"id": "EGvGDVrf"
				},
				{
					"id": "1eEJpS12-ke5fXYPxpo0I",
					"type": "arrow"
				},
				{
					"id": "y5W-ERwUBX6hSM_vPD1y3",
					"type": "arrow"
				},
				{
					"id": "_seBPyu0ytU-lILpBMRTk",
					"type": "arrow"
				},
				{
					"id": "vUftxHAbRM0LxDAmmLJW5",
					"type": "arrow"
				},
				{
					"id": "KfhCZBf2OtKa5FhbROzRI",
					"type": "arrow"
				}
			],
			"updated": 1734618077582,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 774,
			"versionNonce": 88509474,
			"isDeleted": false,
			"id": "zoVv-N5zBHuoUo0DcypWu",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -423.26117904773923,
			"y": -738.1497650388199,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 322.29773630161856,
			"height": 76.61263407621298,
			"seed": 1651464354,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"type": "text",
					"id": "dv047gln"
				},
				{
					"id": "y5W-ERwUBX6hSM_vPD1y3",
					"type": "arrow"
				},
				{
					"id": "ERa1RcIuduGW9QSTQWNh1",
					"type": "arrow"
				}
			],
			"updated": 1734618174213,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 673,
			"versionNonce": 1051104610,
			"isDeleted": false,
			"id": "f3bnwQPe6mBRwpxK8sIB-",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -18.792811500407197,
			"y": -743.0332582758917,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 233.0307745483907,
			"height": 81.49612731328487,
			"seed": 1845490786,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"type": "text",
					"id": "bjhqWcfk"
				},
				{
					"id": "_seBPyu0ytU-lILpBMRTk",
					"type": "arrow"
				},
				{
					"id": "dblAGLDDY16RxnUDbVV3p",
					"type": "arrow"
				}
			],
			"updated": 1734618178346,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 1112,
			"versionNonce": 878769378,
			"isDeleted": false,
			"id": "kqqalvxIL1MUBIHwyVzVN",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 298.44469210676243,
			"y": -395.9111083225821,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 288.6860701888022,
			"height": 81.49612731328487,
			"seed": 1015486498,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"type": "text",
					"id": "BAwiAj9Y"
				},
				{
					"id": "vUftxHAbRM0LxDAmmLJW5",
					"type": "arrow"
				},
				{
					"id": "T3VwfdlWDWLqbus2lGqce",
					"type": "arrow"
				},
				{
					"id": "ERa1RcIuduGW9QSTQWNh1",
					"type": "arrow"
				},
				{
					"id": "dblAGLDDY16RxnUDbVV3p",
					"type": "arrow"
				}
			],
			"updated": 1734618207825,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 978,
			"versionNonce": 635840190,
			"isDeleted": false,
			"id": "x1apmRl_mLIQavEc-3aTK",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 136.89097750505994,
			"y": -224.5055080842469,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 607.6004614175229,
			"height": 81.49612731328487,
			"seed": 1039385570,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"type": "text",
					"id": "0iLjJURD"
				},
				{
					"id": "T3VwfdlWDWLqbus2lGqce",
					"type": "arrow"
				},
				{
					"id": "vxI1qhxhbLeIOp5EgCm9L",
					"type": "arrow"
				}
			],
			"updated": 1734618155117,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 978,
			"versionNonce": 420861886,
			"isDeleted": false,
			"id": "_hPZaJ5faORk1HmqwH2W_",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 211.65341277752697,
			"y": -50.40014518768362,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 458.0755908725886,
			"height": 81.49612731328487,
			"seed": 206895010,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"type": "text",
					"id": "1hzNbigD"
				},
				{
					"id": "vxI1qhxhbLeIOp5EgCm9L",
					"type": "arrow"
				}
			],
			"updated": 1734618155117,
			"link": null,
			"locked": false
		},
		{
			"type": "arrow",
			"version": 1554,
			"versionNonce": 1586133118,
			"isDeleted": false,
			"id": "ef6Ulq4ErI8SXKoZx4Gxd",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -119.48963326677958,
			"y": -1530.211760733757,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 7.105427357601002e-14,
			"height": 80.01437954395237,
			"seed": 668578658,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1734617956401,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "aUlOqw6KqPhKn5pyLm710",
				"gap": 1.8521847116655579,
				"focus": -0.0000061477659456270545
			},
			"endBinding": {
				"elementId": "l0uf5VxRwFAmYXFUxCq9a",
				"gap": 10.742671327660219,
				"focus": 0.000004390779360459311
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					-7.105427357601002e-14,
					80.01437954395237
				]
			]
		},
		{
			"type": "arrow",
			"version": 1554,
			"versionNonce": 388188542,
			"isDeleted": false,
			"id": "DCAwl2Qrh3bD6bklZdrlc",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -119.48963326677969,
			"y": -1356.106397837194,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 1.4210854715202004e-14,
			"height": 80.0143795439526,
			"seed": 852555554,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1734617956401,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "l0uf5VxRwFAmYXFUxCq9a",
				"gap": 1.8521847116655294,
				"focus": -0.0000043907793604593104
			},
			"endBinding": {
				"elementId": "z3t7c4c_hiRxXmrqyuY0w",
				"gap": 10.742671327660133,
				"focus": 0.000003856749308767084
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					-1.4210854715202004e-14,
					80.0143795439526
				]
			]
		},
		{
			"type": "arrow",
			"version": 1554,
			"versionNonce": 1781109502,
			"isDeleted": false,
			"id": "yVeSmkSnX0zihdiCSJPK5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -119.48963326677972,
			"y": -1182.0010349406307,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 0,
			"height": 80.01437954395237,
			"seed": 766100194,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1734617956401,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "z3t7c4c_hiRxXmrqyuY0w",
				"gap": 1.8521847116656147,
				"focus": -0.000003856749308767083
			},
			"endBinding": {
				"elementId": "TowUw9AuAjQS56vuzlRmv",
				"gap": 10.742671327660219,
				"focus": 0.000002497992682812831
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					0,
					80.01437954395237
				]
			]
		},
		{
			"type": "arrow",
			"version": 1554,
			"versionNonce": 625654910,
			"isDeleted": false,
			"id": "1eEJpS12-ke5fXYPxpo0I",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -119.48963326677965,
			"y": -1007.8956720440676,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 1.5631940186722204e-13,
			"height": 80.01437954395249,
			"seed": 854791842,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1734617956402,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "TowUw9AuAjQS56vuzlRmv",
				"gap": 1.8521847116655863,
				"focus": -0.0000024979926828128306
			},
			"endBinding": {
				"elementId": "zPQ7qWK58sMJXgQMOaz_F",
				"gap": 10.742671327660219,
				"focus": 0.000005312588938309156
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					1.5631940186722204e-13,
					80.01437954395249
				]
			]
		},
		{
			"type": "arrow",
			"version": 1906,
			"versionNonce": 367314146,
			"isDeleted": false,
			"id": "y5W-ERwUBX6hSM_vPD1y3",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -223.52221373236227,
			"y": -833.7903091475044,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 79.47051248193696,
			"height": 84.89787278102438,
			"seed": 833836578,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1734618112584,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "zPQ7qWK58sMJXgQMOaz_F",
				"focus": 0.2669404377156424,
				"gap": 1.8521847116655863
			},
			"endBinding": {
				"elementId": "zoVv-N5zBHuoUo0DcypWu",
				"focus": -0.3931622103893775,
				"gap": 10.742671327660219
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					-48.67801882759011,
					38.33575845694122
				],
				[
					-79.47051248193696,
					84.89787278102438
				]
			]
		},
		{
			"type": "arrow",
			"version": 1882,
			"versionNonce": 447334398,
			"isDeleted": false,
			"id": "_seBPyu0ytU-lILpBMRTk",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -15.4586962138211,
			"y": -834.2962005409471,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 113.1805529945859,
			"height": 80.01437954395249,
			"seed": 2129150434,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1734618115412,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "zPQ7qWK58sMJXgQMOaz_F",
				"focus": -0.07620826378551149,
				"gap": 1.3462933182229335
			},
			"endBinding": {
				"elementId": "f3bnwQPe6mBRwpxK8sIB-",
				"focus": 0.31699288355765576,
				"gap": 11.248562721102871
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					69.0169499410921,
					33.286576764150595
				],
				[
					113.1805529945859,
					80.01437954395249
				]
			]
		},
		{
			"type": "arrow",
			"version": 3553,
			"versionNonce": 1466868834,
			"isDeleted": false,
			"id": "vUftxHAbRM0LxDAmmLJW5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -231.2734302557255,
			"y": -418.4578444499373,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 520.740969888418,
			"height": 57.323370655714086,
			"seed": 1980347810,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1734618207826,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "GXe56fbe9Qves0OYbKe4Y",
				"focus": -0.8319299182642476,
				"gap": 16.065245781429212
			},
			"endBinding": {
				"elementId": "kqqalvxIL1MUBIHwyVzVN",
				"gap": 8.977152474069953,
				"focus": -0.22451632524250018
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					280.62387317101866,
					27.296953046059457
				],
				[
					520.740969888418,
					57.323370655714086
				]
			]
		},
		{
			"type": "arrow",
			"version": 3196,
			"versionNonce": 1064727522,
			"isDeleted": false,
			"id": "T3VwfdlWDWLqbus2lGqce",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 442.219276048394,
			"y": -312.56279629763185,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 0.917336781763197,
			"height": 77.31461688572472,
			"seed": 944157026,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1734618207826,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "kqqalvxIL1MUBIHwyVzVN",
				"gap": 1.852184711665359,
				"focus": 0.000001789909387494446
			},
			"endBinding": {
				"elementId": "x1apmRl_mLIQavEc-3aTK",
				"gap": 10.742671327660219,
				"focus": -6.761896707061438e-7
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					-0.917336781763197,
					77.31461688572472
				]
			]
		},
		{
			"type": "arrow",
			"version": 2930,
			"versionNonce": 23873826,
			"isDeleted": false,
			"id": "vxI1qhxhbLeIOp5EgCm9L",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 440.6910027872434,
			"y": -141.15719605929644,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 2.2737367544323206e-13,
			"height": 80.0143795439526,
			"seed": 1760441634,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1734618155182,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "x1apmRl_mLIQavEc-3aTK",
				"focus": 6.761896703076732e-7,
				"gap": 1.8521847116655863
			},
			"endBinding": {
				"elementId": "_hPZaJ5faORk1HmqwH2W_",
				"focus": -8.96911262318503e-7,
				"gap": 10.742671327660219
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					-2.2737367544323206e-13,
					80.0143795439526
				]
			]
		},
		{
			"type": "text",
			"version": 522,
			"versionNonce": 1648437118,
			"isDeleted": false,
			"id": "PfsUKXRS",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -164.76378975980293,
			"y": -1585.312009102065,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 90.546875,
			"height": 25,
			"seed": 1768898786,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1734617956400,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 5,
			"text": "Start Script",
			"rawText": "Start Script",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "aUlOqw6KqPhKn5pyLm710",
			"originalText": "Start Script",
			"lineHeight": 1.25,
			"baseline": 19
		},
		{
			"type": "text",
			"version": 522,
			"versionNonce": 684257534,
			"isDeleted": false,
			"id": "2Ed5u2mJ",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -187.91320382230262,
			"y": -1411.206646205502,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 136.845703125,
			"height": 25,
			"seed": 358143138,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1734617956401,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 5,
			"text": "Parse Arguments",
			"rawText": "Parse Arguments",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "l0uf5VxRwFAmYXFUxCq9a",
			"originalText": "Parse Arguments",
			"lineHeight": 1.25,
			"baseline": 19
		},
		{
			"type": "text",
			"version": 522,
			"versionNonce": 676043390,
			"isDeleted": false,
			"id": "8pdjjqPb",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -196.98058663480265,
			"y": -1237.1012833089387,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 154.98046875,
			"height": 25,
			"seed": 2119823458,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1734617956401,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 5,
			"text": "Environment Setup",
			"rawText": "Environment Setup",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "z3t7c4c_hiRxXmrqyuY0w",
			"originalText": "Environment Setup",
			"lineHeight": 1.25,
			"baseline": 19
		},
		{
			"type": "text",
			"version": 522,
			"versionNonce": 1596007422,
			"isDeleted": false,
			"id": "e0TIxuPV",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -241.94640694730265,
			"y": -1062.9959204123757,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 244.912109375,
			"height": 25,
			"seed": 675386402,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1734617956402,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 5,
			"text": "Initialize Agent and Optimizer",
			"rawText": "Initialize Agent and Optimizer",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "TowUw9AuAjQS56vuzlRmv",
			"originalText": "Initialize Agent and Optimizer",
			"lineHeight": 1.25,
			"baseline": 19
		},
		{
			"type": "text",
			"version": 522,
			"versionNonce": 1860093438,
			"isDeleted": false,
			"id": "EGvGDVrf",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -177.1856647598028,
			"y": -888.8905575158125,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 115.390625,
			"height": 25,
			"seed": 1157545954,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1734617956402,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 5,
			"text": "Training Loop",
			"rawText": "Training Loop",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "zPQ7qWK58sMJXgQMOaz_F",
			"originalText": "Training Loop",
			"lineHeight": 1.25,
			"baseline": 19
		},
		{
			"type": "text",
			"version": 774,
			"versionNonce": 1380146878,
			"isDeleted": false,
			"id": "dv047gln",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -364.50977183442996,
			"y": -712.3434480007134,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 204.794921875,
			"height": 25,
			"seed": 1889563554,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1734617956402,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 5,
			"text": "Evaluate During Training",
			"rawText": "Evaluate During Training",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "zoVv-N5zBHuoUo0DcypWu",
			"originalText": "Evaluate During Training",
			"lineHeight": 1.25,
			"baseline": 19
		},
		{
			"type": "text",
			"version": 673,
			"versionNonce": 1262333822,
			"isDeleted": false,
			"id": "bjhqWcfk",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 48.56730233628815,
			"y": -714.7851946192493,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 98.310546875,
			"height": 25,
			"seed": 1834332002,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1734617956403,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 5,
			"text": "Log Metrics",
			"rawText": "Log Metrics",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "f3bnwQPe6mBRwpxK8sIB-",
			"originalText": "Log Metrics",
			"lineHeight": 1.25,
			"baseline": 19
		},
		{
			"type": "text",
			"version": 1129,
			"versionNonce": 2146699426,
			"isDeleted": false,
			"id": "BAwiAj9Y",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 354.9877928139565,
			"y": -367.66304466593965,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 175.59986877441406,
			"height": 25,
			"seed": 1601008418,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1734618207825,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 5,
			"text": "Optional: Save Model",
			"rawText": "Optional: Save Model",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "kqqalvxIL1MUBIHwyVzVN",
			"originalText": "Optional: Save Model",
			"lineHeight": 1.25,
			"baseline": 19
		},
		{
			"type": "text",
			"version": 980,
			"versionNonce": 640589566,
			"isDeleted": false,
			"id": "0iLjJURD",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 309.89042696382137,
			"y": -196.25744442760447,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 261.6015625,
			"height": 25,
			"seed": 156679906,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1734618155117,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 5,
			"text": "Optional: Evaluate Saved Model",
			"rawText": "Optional: Evaluate Saved Model",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "x1apmRl_mLIQavEc-3aTK",
			"originalText": "Optional: Evaluate Saved Model",
			"lineHeight": 1.25,
			"baseline": 19
		},
		{
			"type": "text",
			"version": 980,
			"versionNonce": 1514156030,
			"isDeleted": false,
			"id": "1hzNbigD",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 342.37089571382126,
			"y": -22.152081531041176,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 196.640625,
			"height": 25,
			"seed": 127963810,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1734618155117,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 5,
			"text": "Optional: Upload Model",
			"rawText": "Optional: Upload Model",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "_hPZaJ5faORk1HmqwH2W_",
			"originalText": "Optional: Upload Model",
			"lineHeight": 1.25,
			"baseline": 19
		},
		{
			"type": "rectangle",
			"version": 323,
			"versionNonce": 1252794558,
			"isDeleted": false,
			"id": "mEiDTm_dBMCd9nbVdzmOR",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -767.3704983588193,
			"y": -532.5919566543798,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 226.484375,
			"height": 44,
			"seed": 217706082,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"type": "text",
					"id": "eKFqP4Kw"
				},
				{
					"id": "615Z5dqRZwJ1dRudWZJo6",
					"type": "arrow"
				}
			],
			"updated": 1734617956032,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 324,
			"versionNonce": 1948604670,
			"isDeleted": false,
			"id": "S3n02zoTg9OcqlTUJodrg",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -789.9642483588193,
			"y": -438.5919566543798,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 271.671875,
			"height": 44,
			"seed": 506581538,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"type": "text",
					"id": "Ptl3HE4f"
				},
				{
					"id": "615Z5dqRZwJ1dRudWZJo6",
					"type": "arrow"
				},
				{
					"id": "4pFY1Qu65DnetWV3TtMOF",
					"type": "arrow"
				}
			],
			"updated": 1734617956033,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 324,
			"versionNonce": 1112377662,
			"isDeleted": false,
			"id": "g7HdqqIhPDIiuVrFQZfKn",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -749.3236233588193,
			"y": -344.5919566543798,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 190.390625,
			"height": 44,
			"seed": 1312243170,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"type": "text",
					"id": "ldOVN9kO"
				},
				{
					"id": "4pFY1Qu65DnetWV3TtMOF",
					"type": "arrow"
				},
				{
					"id": "X7tT1laVT2TYg3_CjIhPa",
					"type": "arrow"
				}
			],
			"updated": 1734617956033,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 324,
			"versionNonce": 881176958,
			"isDeleted": false,
			"id": "q3Hi_r-_G1Q0kDG8vhZn_",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -975.6283108588193,
			"y": -250.59195665437983,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 643,
			"height": 44,
			"seed": 2048471458,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"type": "text",
					"id": "0bpzDQi3"
				},
				{
					"id": "X7tT1laVT2TYg3_CjIhPa",
					"type": "arrow"
				},
				{
					"id": "D143duNvHqB5zZR_t5HtX",
					"type": "arrow"
				}
			],
			"updated": 1734617956033,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 324,
			"versionNonce": 906940862,
			"isDeleted": false,
			"id": "5BBlmnhSB2POAO7UvAnZq",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -808.0579983588193,
			"y": -156.59195665437983,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 307.859375,
			"height": 44,
			"seed": 84323682,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"type": "text",
					"id": "azpemZa9"
				},
				{
					"id": "D143duNvHqB5zZR_t5HtX",
					"type": "arrow"
				},
				{
					"id": "0oDC4lLsLkbJOH0EgJv9b",
					"type": "arrow"
				}
			],
			"updated": 1734617956033,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 324,
			"versionNonce": 571075070,
			"isDeleted": false,
			"id": "KcvWq8ZZh0_pS__-o_48x",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -772.2845608588193,
			"y": -62.59195665437983,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 236.3125,
			"height": 44,
			"seed": 340701474,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"type": "text",
					"id": "UIDHOeih"
				},
				{
					"id": "0oDC4lLsLkbJOH0EgJv9b",
					"type": "arrow"
				},
				{
					"id": "0dbPkZfFUC_feHw_sxdyE",
					"type": "arrow"
				}
			],
			"updated": 1734617956033,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 324,
			"versionNonce": 1199045182,
			"isDeleted": false,
			"id": "uzQciphCPzFiNHceQV-Ru",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -747.2923733588193,
			"y": 31.40804334562017,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 186.328125,
			"height": 44,
			"seed": 1264598242,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"type": "text",
					"id": "V0K5tJqR"
				},
				{
					"id": "0dbPkZfFUC_feHw_sxdyE",
					"type": "arrow"
				},
				{
					"id": "PIvojcZAPkAg2O4N2edeb",
					"type": "arrow"
				}
			],
			"updated": 1734617956033,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 324,
			"versionNonce": 1832518270,
			"isDeleted": false,
			"id": "wLhBuMlEHmMhmnbaTE-Px",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -767.4642483588193,
			"y": 125.40804334562017,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 226.671875,
			"height": 44,
			"seed": 130699426,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"type": "text",
					"id": "M0vDxDu4"
				},
				{
					"id": "PIvojcZAPkAg2O4N2edeb",
					"type": "arrow"
				},
				{
					"id": "EnPfgoBDe-CanydLACtTk",
					"type": "arrow"
				}
			],
			"updated": 1734617956033,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 324,
			"versionNonce": 1443955390,
			"isDeleted": false,
			"id": "Tw96zsN213FEdhfuPVPk_",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -800.6361233588193,
			"y": 219.40804334562017,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 293.015625,
			"height": 44,
			"seed": 490466402,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"type": "text",
					"id": "6082HVHf"
				},
				{
					"id": "EnPfgoBDe-CanydLACtTk",
					"type": "arrow"
				},
				{
					"id": "gb6K3u25P802z7XYF6_PY",
					"type": "arrow"
				}
			],
			"updated": 1734617956033,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 324,
			"versionNonce": 1151204094,
			"isDeleted": false,
			"id": "3EpN7SV8RhtU-MnGbHW8k",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -771.0501858588193,
			"y": 313.4080433456202,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 233.84375,
			"height": 44,
			"seed": 293867554,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"type": "text",
					"id": "kYqIhnjh"
				},
				{
					"id": "gb6K3u25P802z7XYF6_PY",
					"type": "arrow"
				},
				{
					"id": "ZXFE1y1hqcHmC2jTmWRPo",
					"type": "arrow"
				}
			],
			"updated": 1734617956033,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 324,
			"versionNonce": 2137123646,
			"isDeleted": false,
			"id": "2UHSLCciScEQePrxz6UfS",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -741.0736233588193,
			"y": 407.4080433456204,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 173.890625,
			"height": 44,
			"seed": 1485945826,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"type": "text",
					"id": "zwh8iX14"
				},
				{
					"id": "ZXFE1y1hqcHmC2jTmWRPo",
					"type": "arrow"
				},
				{
					"id": "_tyo71aafU-KglE3_EnIq",
					"type": "arrow"
				}
			],
			"updated": 1734617956033,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 324,
			"versionNonce": 1421726590,
			"isDeleted": false,
			"id": "t6TY471XGtOfSioigGq7Z",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -855.0267483588193,
			"y": 501.4080433456204,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 401.796875,
			"height": 44,
			"seed": 276033442,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"type": "text",
					"id": "aGlIliht"
				},
				{
					"id": "_tyo71aafU-KglE3_EnIq",
					"type": "arrow"
				},
				{
					"id": "L44SspKFpdCZzBbkzVwha",
					"type": "arrow"
				}
			],
			"updated": 1734617956033,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 324,
			"versionNonce": 519222206,
			"isDeleted": false,
			"id": "LDUDOMj1Pf43kXvPbVb-X",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -852.3704983588193,
			"y": 595.4080433456204,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 396.484375,
			"height": 44,
			"seed": 1029286754,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"type": "text",
					"id": "c78FNmqm"
				},
				{
					"id": "L44SspKFpdCZzBbkzVwha",
					"type": "arrow"
				},
				{
					"id": "3Mfj76M45A_uIeyr1ZdA3",
					"type": "arrow"
				}
			],
			"updated": 1734617956033,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 326,
			"versionNonce": 727857982,
			"isDeleted": false,
			"id": "wWIbNDo0LHZHkVkK-Fwpq",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -834.6908108588193,
			"y": 689.4080433456204,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 361.125,
			"height": 35,
			"seed": 93450018,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"type": "text",
					"id": "z0SjWW4w"
				},
				{
					"id": "3Mfj76M45A_uIeyr1ZdA3",
					"type": "arrow"
				},
				{
					"id": "Crx_2TxFhazclA4dQow6H",
					"type": "arrow"
				}
			],
			"updated": 1734618221631,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 324,
			"versionNonce": 1313561662,
			"isDeleted": false,
			"id": "JduiixBy-nbGi5KxmOwCN",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -719.2767483588193,
			"y": 783.4080433456204,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 130.296875,
			"height": 44,
			"seed": 1837873890,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"type": "text",
					"id": "PriIFxEU"
				},
				{
					"id": "Crx_2TxFhazclA4dQow6H",
					"type": "arrow"
				},
				{
					"id": "ohdGI8CVm568KrP_Qen4B",
					"type": "arrow"
				}
			],
			"updated": 1734617956033,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 324,
			"versionNonce": 1196500094,
			"isDeleted": false,
			"id": "MMPf8f4kQYLq0Q0K9fvGr",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -772.9329983588193,
			"y": 877.4080433456204,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 237.609375,
			"height": 44,
			"seed": 332795554,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"type": "text",
					"id": "SLJtAijU"
				},
				{
					"id": "ohdGI8CVm568KrP_Qen4B",
					"type": "arrow"
				},
				{
					"id": "aF6NMrGn_uH8OFws55d2H",
					"type": "arrow"
				}
			],
			"updated": 1734617956033,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 324,
			"versionNonce": 1693705406,
			"isDeleted": false,
			"id": "biVrma-3519QbkPruDQRK",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -816.5345608588193,
			"y": 971.4080433456204,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 324.8125,
			"height": 44,
			"seed": 1830808162,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"type": "text",
					"id": "u6VFifcz"
				},
				{
					"id": "aF6NMrGn_uH8OFws55d2H",
					"type": "arrow"
				},
				{
					"id": "EepcFORCB8E_axvdKzELZ",
					"type": "arrow"
				}
			],
			"updated": 1734617956033,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 323,
			"versionNonce": 2027199742,
			"isDeleted": false,
			"id": "obpA7hFGCGkb4feCHg9gf",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -736.9564358588193,
			"y": 1065.4080433456204,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 165.65625,
			"height": 44,
			"seed": 3690018,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"type": "text",
					"id": "qG91oNxf"
				},
				{
					"id": "EepcFORCB8E_axvdKzELZ",
					"type": "arrow"
				}
			],
			"updated": 1734617956033,
			"link": null,
			"locked": false
		},
		{
			"type": "arrow",
			"version": 962,
			"versionNonce": 422493438,
			"isDeleted": false,
			"id": "615Z5dqRZwJ1dRudWZJo6",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -654.1283108588193,
			"y": -487.5919566543798,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 0,
			"height": 43.200000000000045,
			"seed": 571357666,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1734617956404,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "mEiDTm_dBMCd9nbVdzmOR",
				"gap": 1,
				"focus": 0
			},
			"endBinding": {
				"elementId": "S3n02zoTg9OcqlTUJodrg",
				"gap": 5.7999999999999545,
				"focus": 0
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					0,
					43.200000000000045
				]
			]
		},
		{
			"type": "arrow",
			"version": 962,
			"versionNonce": 2095605374,
			"isDeleted": false,
			"id": "4pFY1Qu65DnetWV3TtMOF",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -654.1283108588193,
			"y": -393.5919566543798,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 0,
			"height": 43.200000000000045,
			"seed": 833662370,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1734617956405,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "S3n02zoTg9OcqlTUJodrg",
				"gap": 1,
				"focus": 0
			},
			"endBinding": {
				"elementId": "g7HdqqIhPDIiuVrFQZfKn",
				"gap": 5.7999999999999545,
				"focus": 0
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					0,
					43.200000000000045
				]
			]
		},
		{
			"type": "arrow",
			"version": 962,
			"versionNonce": 1119154174,
			"isDeleted": false,
			"id": "X7tT1laVT2TYg3_CjIhPa",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -654.1283108588193,
			"y": -299.5919566543798,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 0,
			"height": 43.200000000000045,
			"seed": 1414441314,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1734617956405,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "g7HdqqIhPDIiuVrFQZfKn",
				"gap": 1,
				"focus": 0
			},
			"endBinding": {
				"elementId": "q3Hi_r-_G1Q0kDG8vhZn_",
				"gap": 5.7999999999999545,
				"focus": 0
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					0,
					43.200000000000045
				]
			]
		},
		{
			"type": "arrow",
			"version": 962,
			"versionNonce": 921459070,
			"isDeleted": false,
			"id": "D143duNvHqB5zZR_t5HtX",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -654.1283108588193,
			"y": -205.59195665437983,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 0,
			"height": 43.200000000000045,
			"seed": 825699618,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1734617956405,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "q3Hi_r-_G1Q0kDG8vhZn_",
				"gap": 1,
				"focus": 0
			},
			"endBinding": {
				"elementId": "5BBlmnhSB2POAO7UvAnZq",
				"gap": 5.7999999999999545,
				"focus": 0
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					0,
					43.200000000000045
				]
			]
		},
		{
			"type": "arrow",
			"version": 962,
			"versionNonce": 65446654,
			"isDeleted": false,
			"id": "0oDC4lLsLkbJOH0EgJv9b",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -654.1283108588193,
			"y": -111.59195665437983,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 0,
			"height": 43.200000000000045,
			"seed": 769210594,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1734617956406,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "5BBlmnhSB2POAO7UvAnZq",
				"gap": 1,
				"focus": 0
			},
			"endBinding": {
				"elementId": "KcvWq8ZZh0_pS__-o_48x",
				"gap": 5.7999999999999545,
				"focus": 0
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					0,
					43.200000000000045
				]
			]
		},
		{
			"type": "arrow",
			"version": 962,
			"versionNonce": 838585470,
			"isDeleted": false,
			"id": "0dbPkZfFUC_feHw_sxdyE",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -654.1283108588193,
			"y": -17.591956654379825,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 0,
			"height": 43.200000000000045,
			"seed": 700697762,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1734617956406,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "KcvWq8ZZh0_pS__-o_48x",
				"gap": 1,
				"focus": 0
			},
			"endBinding": {
				"elementId": "uzQciphCPzFiNHceQV-Ru",
				"gap": 5.7999999999999545,
				"focus": 0
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					0,
					43.200000000000045
				]
			]
		},
		{
			"type": "arrow",
			"version": 962,
			"versionNonce": 662951422,
			"isDeleted": false,
			"id": "PIvojcZAPkAg2O4N2edeb",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -654.1283108588193,
			"y": 76.40804334562017,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 0,
			"height": 43.200000000000045,
			"seed": 983951458,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1734617956407,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "uzQciphCPzFiNHceQV-Ru",
				"gap": 1,
				"focus": 0
			},
			"endBinding": {
				"elementId": "wLhBuMlEHmMhmnbaTE-Px",
				"gap": 5.7999999999999545,
				"focus": 0
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					0,
					43.200000000000045
				]
			]
		},
		{
			"type": "arrow",
			"version": 962,
			"versionNonce": 685162366,
			"isDeleted": false,
			"id": "EnPfgoBDe-CanydLACtTk",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -654.1283108588193,
			"y": 170.40804334562017,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 0,
			"height": 43.200000000000045,
			"seed": 1749978146,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1734617956407,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "wLhBuMlEHmMhmnbaTE-Px",
				"gap": 1,
				"focus": 0
			},
			"endBinding": {
				"elementId": "Tw96zsN213FEdhfuPVPk_",
				"gap": 5.7999999999999545,
				"focus": 0
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					0,
					43.200000000000045
				]
			]
		},
		{
			"type": "arrow",
			"version": 962,
			"versionNonce": 1481410814,
			"isDeleted": false,
			"id": "gb6K3u25P802z7XYF6_PY",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -654.1283108588193,
			"y": 264.4080433456202,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 0,
			"height": 43.19999999999993,
			"seed": 1756149730,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1734617956407,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "Tw96zsN213FEdhfuPVPk_",
				"gap": 1,
				"focus": 0
			},
			"endBinding": {
				"elementId": "3EpN7SV8RhtU-MnGbHW8k",
				"gap": 5.800000000000068,
				"focus": 0
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					0,
					43.19999999999993
				]
			]
		},
		{
			"type": "arrow",
			"version": 962,
			"versionNonce": 909980286,
			"isDeleted": false,
			"id": "ZXFE1y1hqcHmC2jTmWRPo",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -654.1283108588193,
			"y": 358.4080433456202,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 0,
			"height": 43.200000000000045,
			"seed": 1540320162,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1734617956408,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "3EpN7SV8RhtU-MnGbHW8k",
				"gap": 1,
				"focus": 0
			},
			"endBinding": {
				"elementId": "2UHSLCciScEQePrxz6UfS",
				"gap": 5.800000000000182,
				"focus": 0
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					0,
					43.200000000000045
				]
			]
		},
		{
			"type": "arrow",
			"version": 962,
			"versionNonce": 553696254,
			"isDeleted": false,
			"id": "_tyo71aafU-KglE3_EnIq",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -654.1283108588193,
			"y": 452.4080433456204,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 0,
			"height": 43.19999999999982,
			"seed": 132491106,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1734617956408,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "2UHSLCciScEQePrxz6UfS",
				"gap": 1,
				"focus": 0
			},
			"endBinding": {
				"elementId": "t6TY471XGtOfSioigGq7Z",
				"gap": 5.800000000000182,
				"focus": 0
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					0,
					43.19999999999982
				]
			]
		},
		{
			"type": "arrow",
			"version": 962,
			"versionNonce": 1424958846,
			"isDeleted": false,
			"id": "L44SspKFpdCZzBbkzVwha",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -654.1283108588193,
			"y": 546.4080433456204,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 0,
			"height": 43.19999999999982,
			"seed": 356412194,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1734617956408,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "t6TY471XGtOfSioigGq7Z",
				"gap": 1,
				"focus": 0
			},
			"endBinding": {
				"elementId": "LDUDOMj1Pf43kXvPbVb-X",
				"gap": 5.800000000000182,
				"focus": 0
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					0,
					43.19999999999982
				]
			]
		},
		{
			"type": "arrow",
			"version": 964,
			"versionNonce": 621977378,
			"isDeleted": false,
			"id": "3Mfj76M45A_uIeyr1ZdA3",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -654.1283108588193,
			"y": 640.4080433456204,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 0,
			"height": 43.19999999999982,
			"seed": 1246279394,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1734618222208,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "LDUDOMj1Pf43kXvPbVb-X",
				"gap": 1,
				"focus": 0
			},
			"endBinding": {
				"elementId": "wWIbNDo0LHZHkVkK-Fwpq",
				"gap": 5.800000000000182,
				"focus": 0
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					0,
					43.19999999999982
				]
			]
		},
		{
			"type": "arrow",
			"version": 964,
			"versionNonce": 1860877986,
			"isDeleted": false,
			"id": "Crx_2TxFhazclA4dQow6H",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -654.1283108588193,
			"y": 725.4080433456204,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 0,
			"height": 52.19999999999982,
			"seed": 1200851618,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1734618222208,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "wWIbNDo0LHZHkVkK-Fwpq",
				"gap": 1,
				"focus": 0
			},
			"endBinding": {
				"elementId": "JduiixBy-nbGi5KxmOwCN",
				"gap": 5.800000000000182,
				"focus": 0
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					0,
					52.19999999999982
				]
			]
		},
		{
			"type": "arrow",
			"version": 962,
			"versionNonce": 86745598,
			"isDeleted": false,
			"id": "ohdGI8CVm568KrP_Qen4B",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -654.1283108588193,
			"y": 828.4080433456204,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 0,
			"height": 43.19999999999982,
			"seed": 1137567330,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1734617956409,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "JduiixBy-nbGi5KxmOwCN",
				"gap": 1,
				"focus": 0
			},
			"endBinding": {
				"elementId": "MMPf8f4kQYLq0Q0K9fvGr",
				"gap": 5.800000000000182,
				"focus": 0
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					0,
					43.19999999999982
				]
			]
		},
		{
			"type": "arrow",
			"version": 962,
			"versionNonce": 288721790,
			"isDeleted": false,
			"id": "aF6NMrGn_uH8OFws55d2H",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -654.1283108588193,
			"y": 922.4080433456204,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 0,
			"height": 43.19999999999982,
			"seed": 1204210210,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1734617956410,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "MMPf8f4kQYLq0Q0K9fvGr",
				"gap": 1,
				"focus": 0
			},
			"endBinding": {
				"elementId": "biVrma-3519QbkPruDQRK",
				"gap": 5.800000000000182,
				"focus": 0
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					0,
					43.19999999999982
				]
			]
		},
		{
			"type": "arrow",
			"version": 962,
			"versionNonce": 371348734,
			"isDeleted": false,
			"id": "EepcFORCB8E_axvdKzELZ",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -654.1283108588193,
			"y": 1016.4080433456204,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 0,
			"height": 43.19999999999982,
			"seed": 1785542114,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1734617956410,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "biVrma-3519QbkPruDQRK",
				"gap": 1,
				"focus": 0
			},
			"endBinding": {
				"elementId": "obpA7hFGCGkb4feCHg9gf",
				"gap": 5.800000000000182,
				"focus": 0
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					0,
					43.19999999999982
				]
			]
		},
		{
			"type": "text",
			"version": 326,
			"versionNonce": 1102267518,
			"isDeleted": false,
			"id": "eKFqP4Kw",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -733.2103421088193,
			"y": -523.0919566543798,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 158.1640625,
			"height": 25,
			"seed": 214968738,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1734617956404,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 5,
			"text": "Start Training Loop",
			"rawText": "Start Training Loop",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "mEiDTm_dBMCd9nbVdzmOR",
			"originalText": "Start Training Loop",
			"lineHeight": 1.25,
			"baseline": 19
		},
		{
			"type": "text",
			"version": 326,
			"versionNonce": 356601342,
			"isDeleted": false,
			"id": "Ptl3HE4f",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -745.4076077338193,
			"y": -429.0919566543798,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 182.55859375,
			"height": 25,
			"seed": 371107170,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1734617956404,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 5,
			"text": "Iterate Over Timesteps",
			"rawText": "Iterate Over Timesteps",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "S3n02zoTg9OcqlTUJodrg",
			"originalText": "Iterate Over Timesteps",
			"lineHeight": 1.25,
			"baseline": 19
		},
		{
			"type": "text",
			"version": 326,
			"versionNonce": 941242238,
			"isDeleted": false,
			"id": "ldOVN9kO",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -719.4066311713193,
			"y": -335.0919566543798,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 130.556640625,
			"height": 25,
			"seed": 799516962,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1734617956405,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 5,
			"text": "Collect Rollouts",
			"rawText": "Collect Rollouts",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "g7HdqqIhPDIiuVrFQZfKn",
			"originalText": "Collect Rollouts",
			"lineHeight": 1.25,
			"baseline": 19
		},
		{
			"type": "text",
			"version": 326,
			"versionNonce": 748028158,
			"isDeleted": false,
			"id": "0bpzDQi3",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -885.4857327338193,
			"y": -241.09195665437983,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 462.71484375,
			"height": 25,
			"seed": 14300386,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1734617956405,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 5,
			"text": "Store Observations, Actions, Rewards, Values, Log-Probs",
			"rawText": "Store Observations, Actions, Rewards, Values, Log-Probs",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "q3Hi_r-_G1Q0kDG8vhZn_",
			"originalText": "Store Observations, Actions, Rewards, Values, Log-Probs",
			"lineHeight": 1.25,
			"baseline": 19
		},
		{
			"type": "text",
			"version": 326,
			"versionNonce": 1393339006,
			"isDeleted": false,
			"id": "azpemZa9",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -764.3919827338193,
			"y": -147.09195665437983,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 220.52734375,
			"height": 25,
			"seed": 1799702690,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1734617956405,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 5,
			"text": "Compute GAE and Returns",
			"rawText": "Compute GAE and Returns",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "5BBlmnhSB2POAO7UvAnZq",
			"originalText": "Compute GAE and Returns",
			"lineHeight": 1.25,
			"baseline": 19
		},
		{
			"type": "text",
			"version": 326,
			"versionNonce": 1775645694,
			"isDeleted": false,
			"id": "UIDHOeih",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -734.0892483588193,
			"y": -53.09195665437983,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 159.921875,
			"height": 25,
			"seed": 1184359522,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1734617956406,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 5,
			"text": "Iterate Over Epochs",
			"rawText": "Iterate Over Epochs",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "KcvWq8ZZh0_pS__-o_48x",
			"originalText": "Iterate Over Epochs",
			"lineHeight": 1.25,
			"baseline": 19
		},
		{
			"type": "text",
			"version": 326,
			"versionNonce": 222993790,
			"isDeleted": false,
			"id": "V0K5tJqR",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -718.2884671088193,
			"y": 40.90804334562017,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 128.3203125,
			"height": 25,
			"seed": 480315426,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1734617956406,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 5,
			"text": "Batch Sampling",
			"rawText": "Batch Sampling",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "uzQciphCPzFiNHceQV-Ru",
			"originalText": "Batch Sampling",
			"lineHeight": 1.25,
			"baseline": 19
		},
		{
			"type": "text",
			"version": 326,
			"versionNonce": 935454462,
			"isDeleted": false,
			"id": "M0vDxDu4",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -734.1234280463193,
			"y": 134.90804334562017,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 159.990234375,
			"height": 25,
			"seed": 1699722210,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1734617956407,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 5,
			"text": "Calculate PPO Loss",
			"rawText": "Calculate PPO Loss",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "wLhBuMlEHmMhmnbaTE-Px",
			"originalText": "Calculate PPO Loss",
			"lineHeight": 1.25,
			"baseline": 19
		},
		{
			"type": "text",
			"version": 326,
			"versionNonce": 1100222590,
			"isDeleted": false,
			"id": "6082HVHf",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -755.7689358588193,
			"y": 228.90804334562017,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 203.28125,
			"height": 25,
			"seed": 1119020962,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1734617956407,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 5,
			"text": "Surrogate Objective Loss",
			"rawText": "Surrogate Objective Loss",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "Tw96zsN213FEdhfuPVPk_",
			"originalText": "Surrogate Objective Loss",
			"lineHeight": 1.25,
			"baseline": 19
		},
		{
			"type": "text",
			"version": 326,
			"versionNonce": 1629035006,
			"isDeleted": false,
			"id": "kYqIhnjh",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -736.3451077338193,
			"y": 322.9080433456202,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 164.43359375,
			"height": 25,
			"seed": 1022993250,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1734617956408,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 5,
			"text": "Value Function Loss",
			"rawText": "Value Function Loss",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "3EpN7SV8RhtU-MnGbHW8k",
			"originalText": "Value Function Loss",
			"lineHeight": 1.25,
			"baseline": 19
		},
		{
			"type": "text",
			"version": 326,
			"versionNonce": 715719550,
			"isDeleted": false,
			"id": "zwh8iX14",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -714.4066311713193,
			"y": 416.9080433456204,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 120.556640625,
			"height": 25,
			"seed": 2121459490,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1734617956408,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 5,
			"text": "Entropy Bonus",
			"rawText": "Entropy Bonus",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "2UHSLCciScEQePrxz6UfS",
			"originalText": "Entropy Bonus",
			"lineHeight": 1.25,
			"baseline": 19
		},
		{
			"type": "text",
			"version": 326,
			"versionNonce": 278646014,
			"isDeleted": false,
			"id": "aGlIliht",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -794.6458889838193,
			"y": 510.9080433456204,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 281.03515625,
			"height": 25,
			"seed": 260944610,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1734617956408,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 5,
			"text": "Backpropagation and Optimization",
			"rawText": "Backpropagation and Optimization",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "t6TY471XGtOfSioigGq7Z",
			"originalText": "Backpropagation and Optimization",
			"lineHeight": 1.25,
			"baseline": 19
		},
		{
			"type": "text",
			"version": 326,
			"versionNonce": 1665758846,
			"isDeleted": false,
			"id": "c78FNmqm",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -794.6507717963193,
			"y": 604.9080433456204,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 281.044921875,
			"height": 25,
			"seed": 316212898,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1734617956409,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 5,
			"text": "Update Policy and Value Networks",
			"rawText": "Update Policy and Value Networks",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "LDUDOMj1Pf43kXvPbVb-X",
			"originalText": "Update Policy and Value Networks",
			"lineHeight": 1.25,
			"baseline": 19
		},
		{
			"type": "text",
			"version": 349,
			"versionNonce": 2120764158,
			"isDeleted": false,
			"id": "z0SjWW4w",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -783.7882229681943,
			"y": 694.4080433456204,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 259.31982421875,
			"height": 25,
			"seed": 17031778,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1734618221631,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 5,
			"text": "Optional: Update Learning Rate",
			"rawText": "Optional: Update Learning Rate",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "wWIbNDo0LHZHkVkK-Fwpq",
			"originalText": "Optional: Update Learning Rate",
			"lineHeight": 1.25,
			"baseline": 19
		},
		{
			"type": "text",
			"version": 326,
			"versionNonce": 1714776446,
			"isDeleted": false,
			"id": "PriIFxEU",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -698.2835842963193,
			"y": 792.9080433456204,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 88.310546875,
			"height": 25,
			"seed": 1692223010,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1734617956409,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 5,
			"text": "End Epoch",
			"rawText": "End Epoch",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "JduiixBy-nbGi5KxmOwCN",
			"originalText": "End Epoch",
			"lineHeight": 1.25,
			"baseline": 19
		},
		{
			"type": "text",
			"version": 326,
			"versionNonce": 220443390,
			"isDeleted": false,
			"id": "SLJtAijU",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -739.8704983588193,
			"y": 886.9080433456204,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 171.484375,
			"height": 25,
			"seed": 391393762,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1734617956409,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 5,
			"text": "Log Training Metrics",
			"rawText": "Log Training Metrics",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "MMPf8f4kQYLq0Q0K9fvGr",
			"originalText": "Log Training Metrics",
			"lineHeight": 1.25,
			"baseline": 19
		},
		{
			"type": "text",
			"version": 326,
			"versionNonce": 237821054,
			"isDeleted": false,
			"id": "u6VFifcz",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -771.0619046088193,
			"y": 980.9080433456204,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 233.8671875,
			"height": 25,
			"seed": 2071438754,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1734617956410,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 5,
			"text": "Save Rollouts for Debugging",
			"rawText": "Save Rollouts for Debugging",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "biVrma-3519QbkPruDQRK",
			"originalText": "Save Rollouts for Debugging",
			"lineHeight": 1.25,
			"baseline": 19
		},
		{
			"type": "text",
			"version": 326,
			"versionNonce": 7581054,
			"isDeleted": false,
			"id": "qG91oNxf",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -709.6019436713193,
			"y": 1074.9080433456204,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 110.947265625,
			"height": 25,
			"seed": 980853090,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1734617956410,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 5,
			"text": "End Timestep",
			"rawText": "End Timestep",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "obpA7hFGCGkb4feCHg9gf",
			"originalText": "End Timestep",
			"lineHeight": 1.25,
			"baseline": 19
		},
		{
			"type": "rectangle",
			"version": 1117,
			"versionNonce": 1218463394,
			"isDeleted": false,
			"id": "iTLl1g_HV1wnCP9aRj4X9",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -799.8411496052806,
			"y": -736.861452489057,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 322.29773630161856,
			"height": 76.61263407621298,
			"seed": 2141201698,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"type": "text",
					"id": "SDULvO24"
				},
				{
					"id": "KfhCZBf2OtKa5FhbROzRI",
					"type": "arrow"
				}
			],
			"updated": 1734618077582,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 1136,
			"versionNonce": 534214206,
			"isDeleted": false,
			"id": "SDULvO24",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -695.2743127044714,
			"y": -711.0551354509505,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 113.1640625,
			"height": 25,
			"seed": 878915810,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1734617956410,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 5,
			"text": "Training logic",
			"rawText": "Training logic",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "iTLl1g_HV1wnCP9aRj4X9",
			"originalText": "Training logic",
			"lineHeight": 1.25,
			"baseline": 19
		},
		{
			"type": "line",
			"version": 705,
			"versionNonce": 140955262,
			"isDeleted": false,
			"id": "LHXbqW_D2svn8oN0uu-Nd",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1090.0336145442727,
			"y": -550.2502071934675,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 447.09199051909616,
			"height": 105.36198098320004,
			"seed": 1011795106,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1734617956034,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					80.06197579716165,
					-70.31614421035651
				],
				[
					399.0272496658556,
					-76.09629766197568
				],
				[
					447.09199051909616,
					-105.36198098320004
				]
			]
		},
		{
			"type": "line",
			"version": 1276,
			"versionNonce": 163860158,
			"isDeleted": false,
			"id": "-Gn2_lR_NoHXIcZrBgpuJ",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -177.11991207775804,
			"y": -548.9765266161414,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 467.88537686910297,
			"height": 106.15834209897938,
			"seed": 823255138,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1734617956034,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-83.78550390770192,
					-70.84761716234655
				],
				[
					-417.5852376021847,
					-76.67145894830752
				],
				[
					-467.88537686910297,
					-106.15834209897938
				]
			]
		},
		{
			"type": "rectangle",
			"version": 178,
			"versionNonce": 905066686,
			"isDeleted": false,
			"id": "GXe56fbe9Qves0OYbKe4Y",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "dashed",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1035.8489131061199,
			"y": -572.0875565516374,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 788.5102370689651,
			"height": 1732.8663793103447,
			"seed": 511411234,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"id": "vUftxHAbRM0LxDAmmLJW5",
					"type": "arrow"
				}
			],
			"updated": 1734618159693,
			"link": null,
			"locked": false
		},
		{
			"id": "KfhCZBf2OtKa5FhbROzRI",
			"type": "arrow",
			"x": -263.2555293451112,
			"y": -874.1138025356166,
			"width": 361.46260245901635,
			"height": 130.79533811475414,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 862932606,
			"version": 523,
			"versionNonce": 356633662,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1734618108137,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-289.62602459016387,
					69.51844262295083
				],
				[
					-361.46260245901635,
					130.79533811475414
				]
			],
			"lastCommittedPoint": [
				-361.46260245901635,
				130.79533811475414
			],
			"startBinding": {
				"elementId": "zPQ7qWK58sMJXgQMOaz_F",
				"focus": 0.44011569435845,
				"gap": 8.427579591391805
			},
			"endBinding": {
				"elementId": "iTLl1g_HV1wnCP9aRj4X9",
				"focus": -0.1868571975845085,
				"gap": 6.457011931805482
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "ERa1RcIuduGW9QSTQWNh1",
			"type": "arrow",
			"x": -156.47873871551622,
			"y": -651.7905443388959,
			"width": 501.9199867136518,
			"height": 242.95334872380158,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 1817288510,
			"version": 331,
			"versionNonce": 1282433890,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1734618207826,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					501.9199867136518,
					242.95334872380158
				]
			],
			"lastCommittedPoint": [
				497.515368852459,
				240.2535860655737
			],
			"startBinding": {
				"elementId": "zoVv-N5zBHuoUo0DcypWu",
				"gap": 9.746586623710982,
				"focus": -0.026745835644118626
			},
			"endBinding": {
				"elementId": "kqqalvxIL1MUBIHwyVzVN",
				"gap": 12.926087292512193,
				"focus": 0.05924753628385989
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "dblAGLDDY16RxnUDbVV3p",
			"type": "arrow",
			"x": 205.40399616824257,
			"y": -653.2826037651254,
			"width": 235.32228783905092,
			"height": 247.07732413363772,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 2131939326,
			"version": 341,
			"versionNonce": 1079276258,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1734618207826,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					235.32228783905092,
					247.07732413363772
				]
			],
			"lastCommittedPoint": [
				227.7727971311474,
				244.37756147540983
			],
			"startBinding": {
				"elementId": "f3bnwQPe6mBRwpxK8sIB-",
				"gap": 8.25452719748148,
				"focus": -0.39336827830773263
			},
			"endBinding": {
				"elementId": "kqqalvxIL1MUBIHwyVzVN",
				"gap": 10.294171308905561,
				"focus": 0.2541728899672632
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"type": "arrow",
			"version": 3135,
			"versionNonce": 486579646,
			"isDeleted": true,
			"id": "cCix10AyKjvB0ProE2M5I",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -256.47136237863333,
			"y": -851.9710006095683,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 336.7943924947931,
			"height": 108.77101312535012,
			"seed": 861663842,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1734618067824,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "zPQ7qWK58sMJXgQMOaz_F",
				"focus": 0.10230097757009733,
				"gap": 1.6434126249139354
			},
			"endBinding": {
				"elementId": "iTLl1g_HV1wnCP9aRj4X9",
				"focus": -0.23785122915401202,
				"gap": 6.338534995161126
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					-81.36526897427188,
					18.890359950047582
				],
				[
					-241.60102747897383,
					20.90545845256031
				],
				[
					-259.10762704789636,
					75.81224364875504
				],
				[
					-336.7943924947931,
					108.77101312535012
				]
			]
		},
		{
			"id": "FWgD4O5L",
			"type": "text",
			"x": -503.07238985760716,
			"y": -843.5655421570079,
			"width": 10,
			"height": 25,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1109222462,
			"version": 2,
			"versionNonce": 213103074,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1734618061025,
			"link": null,
			"locked": false,
			"text": "",
			"rawText": "",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "middle",
			"baseline": 18,
			"containerId": "cCix10AyKjvB0ProE2M5I",
			"originalText": "",
			"lineHeight": 1.25
		},
		{
			"id": "swXIiHOb",
			"type": "text",
			"x": 313.0553056958722,
			"y": -543.5938230274205,
			"width": 10,
			"height": 25,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 448240318,
			"version": 2,
			"versionNonce": 1787925346,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1734618179433,
			"link": null,
			"locked": false,
			"text": "",
			"rawText": "",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "middle",
			"baseline": 18,
			"containerId": "dblAGLDDY16RxnUDbVV3p",
			"originalText": "",
			"lineHeight": 1.25
		}
	],
	"appState": {
		"theme": "dark",
		"viewBackgroundColor": "#ffffff",
		"currentItemStrokeColor": "#1e1e1e",
		"currentItemBackgroundColor": "transparent",
		"currentItemFillStyle": "solid",
		"currentItemStrokeWidth": 2,
		"currentItemStrokeStyle": "solid",
		"currentItemRoughness": 1,
		"currentItemOpacity": 100,
		"currentItemFontFamily": 1,
		"currentItemFontSize": 20,
		"currentItemTextAlign": "left",
		"currentItemStartArrowhead": null,
		"currentItemEndArrowhead": "arrow",
		"scrollX": 1410.4575115760065,
		"scrollY": 284.15356186649814,
		"zoom": {
			"value": 0.61
		},
		"currentItemRoundness": "round",
		"gridSize": null,
		"gridColor": {
			"Bold": "#C9C9C9FF",
			"Regular": "#EDEDEDFF"
		},
		"currentStrokeOptions": null,
		"previousGridSize": null,
		"frameRendering": {
			"enabled": true,
			"clip": true,
			"name": true,
			"outline": true
		}
	},
	"files": {}
}
```
%%