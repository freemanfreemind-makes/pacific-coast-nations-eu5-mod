Pacific Coast Nations
Mod by TheOneWhoIs

        #################
        Nations included:
        #################

TAG Faction Name        Alt. Name
## V1.0 ##
TLG Tlingit
TMH Tsimshian
XDA Xaayda              Haida
HLA Haisla
HLK Heiltsuk
NUX Nuxalc
OOW Oowekyala           Bella Coola
KWA Kwakiutl            Kwakwakawak
KMK K'omoks             Comox
NOO Nootkah             Nuuchanulth
SQH Squamish
HLM Halkomelem          Halq̓eméylem
WSN WSÁNEĆ              Saanich ##culture stub in game files, no country tag - created as WSN, change if conflict found
LHQ Lhaq'temish         Semiahmoo/Lummi
MKH Makah
LHT Lushootseed
SKL S'Klallam
TWN Twana
TSA Tsamosa
CNK Chinook
KLP Kalapuya
TLK Tillamook
ALX Alsea
COS Coos
NPK Nlakpamuk
LWT Lillooet
TQN Tsilhqot'in
WST Wet'suweten
DKL Dakelh
SWP Secwepemc
SLX Syilix
SNX Sinixt
KTX Ktunaxa
MLA Molalla

## V1.X ##
#

        ###################
        Custom Config Files
        ###################

File
/main_menu/setup/templates/amerindian_northwest_coast.text
/main_menu/setup/templates/amerindian_northwest_interior.text
##amerindian_tribe_settled_northwestern.txt preset exists, but better saved for interior

        #####################
        Modified Config Files
        #####################

File
##Change made
-----------
Change code
-----------

in_game/common/town_setups/00_default.txt
## Added town presets for coastal nation, coastal and interior, paste below to bottom of config file if needed for update
----------------------------
westcoast_town = {
	market_village = 1
	stone_quarry = 1
	tools_guild = 1
	mason = 1
	tar_kiln = 1
	granary = 1
}

westcoast_coastal_town = {
	market_village = 1
	stone_quarry = 1
	tools_guild = 1
	mason = 1
	clay_pit = 1
	salt_collector = 1
}
------------------------------

/in_game/common/advances/3_cabinet_action_unlocks.txt

##add ability to settle adjacent regions


--------------------------------------
settle_the_frontier_advance = {
	icon = expansionism
	age = age_1_traditions
	potential = {
		OR = {
			country_type = location
			country_type = army
		}
		OR = {
			has_or_had_tag = MKU #Makua, is part of Swahili Coast region
			has_or_had_tag = KAM
			original_capital ?= {
				OR = {
					sub_continent = sub_continent:south_america
					sub_continent = sub_continent:central_africa
					region = region:great_lakes_region
					region = region:southern_africa_region
					region = region:zimbabwe_region
					#North American Natives
					region = region:east_coast_region
					region = region:great_plains_region
					region = region:aridoamerica_region ##add this to base file to allow settlement
					region = region:west_coast_region ##add this to base file to allow settlement
					area = area:shiewhibak_area
					continent = continent:oceania
				}
			}
		}
		NOT = { is_subject_type = colonial_nation }
	}
	requires = city_building_advance
	unlock_cabinet_action = settle_the_frontier
}
-----------------------------------------------------------



/in_game/map_data/location_templates.txt


## add any changes here to modify new version of file if Paradox makes any major changes
Location        Changes
saanich         raw_material = stone
pentlatch       raw_material = fruit
saanyaa         raw_material = stone
gwaay_haanas    raw_material = tin
kalapuya        raw_material = fruit
multnomah       raw_material = fruit
nisqually       raw_material = maize
nooksack        raw_material = maize
sto_lo          raw_material = wool
squamish        raw_material = copper
ts_il_kaz_koh   raw_material = fish
st_uxwtews      raw_material = fruit
okanagan        raw_material = fruit
similkameen     raw_material = fruit
q_espiea        raw_material = wild_game
akinkum_asnuq_it raw_material = fruit




/in_game/setup/countries/westcoat.txt


## adds WSN Saanich to map with colour - all other added factions not in base files follow similar formula
------------------------------
#Saanich
WSN = {
	color = map_saanich
	color2 = rgb { 214 113 188 }

	culture_definition = saanich_culture
	religion_definition = salishan_totemism
}
------------------------------

/main_menu/localization/english/country_names_l_english.yml
## Saanich, add after Halkomelem in list
------------------
 WSN: "WSÁNEĆ"
 WSN_ADJ: "WSÁNEĆ"

 #other added faction names:


------------------
## Tsimshian, corrected noun to Tsimshian from "Tsimshia" (wrongly applied latin rules to name)
-------------------
 TMH: "Tsimishian"
 TMH_ADJ: "Tsimishian"

#other corrected names:
 HLM: "Halq̓eméylem"
 HLM_ADJ: "Halq̓eméylem"
 NOO: "Nuuchanulth"
 NOO_ADJ: "Nuuchanulth"
 KWA: "Kwakwak'awak"
 KWA_ADJ: "Kwakwak'awak"
 NPK: "Nlakapamuk"
 NPK_ADJ: "Nlakapamuk"
 LWT: "Lillooet"
 LWT_ADJ: "Lillooet"
 TQN: "Tsilhqot'in"
 TQN_ADJ: "Tsilhqot'in"
 WST: "Wet'suwet'en"
 WST_ADJ: "Wet'suwet'en"
 DKL: "Dakelh"
 DKL_ADJ: "Dakelh"
 SWP: "Secwépemc"
 SWP_ADJ: "Secwépemc"
 SLX: "Syilix"
 SLX_ADJ: "Syilix"
 SNX: "Sinixt"
 SNX_ADJ: "Sinixt"
 KTX: "Ktunaxa"
 KTX_ADJ: "Ktunaxan"
 TLK: "Tillamook"
 TLK_ADJ: "Tillamook"
 ALX: "Alsea"
 ALX_ADJ: "Alsea"
 COS: "Coos"
 COS_ADJ: "Coosian"
 MLA: "Molalla"
 MLA_ADJ: "Molalla"

/main_menu/localization/english/country_history_l_english
## add writeups here when created

/main_menu/localization/english/government_names_l_english.yml
## add language specific titles here when created

/main_menu/setup/start/03_markets.txt
## add after #Tribal North America section
---------------------
	#Westcoast North America
	add_market = kiis_gwaay
	add_market = chinook
---------------------



/main_menu/setup/start/06_pops.txt


## templates for town and rural areas
#Town Coastal - adjust pops up or down as appropriate
-------------------
location_name = {
	define_pop = {	type = nobles	size = 0.020	culture = name_culture	religion = religion_name }
	define_pop = {	type = clergy	size = 0.050	culture = name_culture	religion = religion_name }
	define_pop = {	type = burghers	size = 0.500	culture = name_culture	religion = religion_name }
	define_pop = {	type = peasants	size = 4.000	culture = name_culture	religion = religion_name }
	define_pop = {	type = slaves	size = 1.000	culture = name_rival_culture	religion = religion_name }
}
-------------------
#Rural Coastal - adjust pops up or down as appropriate
-------------------
location_name = {
	define_pop = {	type = tribesmen	size = 2.500	culture = name_culture	religion = religion_name }
	define_pop = {	type = peasants	size = 2.500	culture = name_culture	religion = religion_name }
}
-------------------
#Haida -Specific so that they don't implode 5 years into game
-------------------
kiis_gwaay = {
	define_pop = {	type = nobles	size = 0.020	culture = haida_culture	religion = dene_totemism }
	define_pop = {	type = clergy	size = 0.050	culture = haida_culture	religion = dene_totemism }
	define_pop = {	type = burghers	size = 0.500	culture = haida_culture	religion = dene_totemism }
	define_pop = {	type = peasants	size = 4.250	culture = haida_culture	religion = dene_totemism }
	define_pop = {	type = tribesmen	size = 2.000	culture = haida_culture	religion = dene_totemism }
	define_pop = {	type = slaves	size = 0.750	culture = kwakiutl_culture	religion = dene_totemism }
}
gwaay_haanas = {
	define_pop = {	type = tribesmen	size = 3.000	culture = haida_culture	religion = dene_totemism }
	define_pop = {	type = peasants	size = 4.500	culture = haida_culture	religion = dene_totemism }
}
--------------------



/main_menu/setup/start/westcoast_cities_and_buildings.txt


##add changes as needed
--------------------
	#Westcoast
	kiis_gwaay = { rank = town 		town_setup = westcoast_coastal_town }
	shee_t_ika = { rank = town 		town_setup = westcoast_coastal_town }
	sm_algyax = { rank = town 		town_setup = westcoast_coastal_town }
	haisla = { rank = town 		town_setup = westcoast_coastal_town }
	heiltsuk = { rank = town 		town_setup = westcoast_coastal_town }
	nuxalc = { rank = town 		town_setup = westcoast_coastal_town }
	oweekeno = { rank = town 		town_setup = westcoast_coastal_town }
	ma_amtagila = { rank = town 		town_setup = westcoast_coastal_town }
	k_omoks = { rank = town 		town_setup = westcoast_coastal_town }
	squamish = { rank = town 		town_setup = westcoast_coastal_town }
	ucluelet = { rank = town 		town_setup = westcoast_coastal_town }
	saanich = { rank = town 		town_setup = westcoast_coastal_town }
	whonnock = { rank = town 		town_setup = westcoast_coastal_town }
	lhaq_temish = { rank = town 		town_setup = westcoast_coastal_town }
	puyallup = { rank = town 		town_setup = westcoast_coastal_town }
	twana = { rank = town 		town_setup = westcoast_coastal_town }
	sklallam = { rank = town 		town_setup = westcoast_coastal_town }
	makah = { rank = town 		town_setup = westcoast_coastal_town }
	chehalis = { rank = town 		town_setup = westcoast_coastal_town }
	chinook = { rank = town 		town_setup = westcoast_coastal_town }
	kalapuya = { rank = town 		town_setup = westcoast_town }
	tillamook = { rank = town 		town_setup = westcoast_coastal_town }
	yaquina = { rank = town 		town_setup = westcoast_coastal_town }
	quuiich = { rank = town 		town_setup = westcoast_coastal_town }
	nlaka_pamux = { rank = town 		town_setup = westcoast_coastal_town }
	leel_watr_ool = { rank = town 		town_setup = westcoast_town }
	yunesit_in = { rank = town 		town_setup = westcoast_town }
	wet_suwet_en = { rank = town 		town_setup = westcoast_town }
	nadleh_whuten = { rank = town 		town_setup = westcoast_town }
	tk_emlups = { rank = town 		town_setup = westcoast_town }
	osoyoos = { rank = town 		town_setup = westcoast_town }
	ntiltxitk = { rank = town 		town_setup = westcoast_town }
	aq_am = { rank = town 		town_setup = westcoast_town }
	giiwas = { rank = town 		town_setup = westcoast_town }

-----------------------

/main_menu/localization/english/goods_l_english.yml

add under "slave_market_maintenace":
slave_market_maintenance_basic: "Slave Traders"

------------------------

/in_game/common/building_types/town_buildings.txt

under slave market production methods add

		slave_market_maintenance_basic = {
			leather = 0.35
			tools = 0.3
			weaponry = 0.25
			cloth = 0.5
			slaves_goods = 0.5

			produced = slaves_goods
			output = 1.5

			category = building_maintenance
		}

-----------------------

/main_menu/setup/start/pcn_countries.txt


## paste over entries listed below - add changes as needed - remove faction from 10_countries.txt if factions are from base game to prevent conflicts
-----------------------
#############################
# Pacific Coast Nations - FreeManFreeMind mod
#############################

	#Kalapuya
	KLP = {

		own_control_core = {
			kalapuya atfalati umpqua
		}

		court_language = kalapuyan_language
		capital = kalapuya

		include = "amerindian_northwest_coast"
		include = "expl_northwestern_america"
		government = {
			ruler = random
		}
	}

	#Chinook
	CNK = {

		own_control_core = {
			chinook multnomah watlala
		}

		court_language = chinook_language
		capital = chinook

		include = "amerindian_northwest_coast"
		include = "expl_northwestern_america"
		government = {
			ruler = random
		}
	}

	#Tsamosa
	TSA = {

		own_control_core = {
			chehalis chala_at klikitat stlpulmsh wishram
		}

		court_language = chehalis_language
		capital = chehalis

		include = "amerindian_northwest_coast"
		include = "expl_northwestern_america"
		government = {
			ruler = random
		}
	}

	#Makah
	MKH = {

		own_control_core = {
			makah
		}

		court_language = makah_language
		capital = makah

		include = "amerindian_northwest_coast"
		include = "expl_northwestern_america"
		government = {
			ruler = random
		}
	}


	#S'Klallam
	SKL = {

		own_control_core = {
			sklallam
		}

		court_language = sklallam_language
		capital = sklallam

		include = "amerindian_northwest_coast"
		include = "expl_northwestern_america"
		government = {
			ruler = random
		}
	}

	#Twana
	TWN = {

		own_control_core = {
			twana
		}

		court_language = twana_language
		capital = twana

		include = "amerindian_northwest_coast"
		include = "expl_northwestern_america"
		government = {
			ruler = random
		}
	}

	#Lushootseed
	LHT = {

		own_control_core = {
			duwamish nisqually puyallup skagit snohomish
		}

		court_language = lushootseed_language
		capital = puyallup

		include = "amerindian_northwest_coast"
		include = "expl_northwestern_america"
		government = {
			ruler = random
		}
	}

	#Lhaq'temish
	LHQ = {

		own_control_core = {
			lhaq_temish
		}

		court_language = lummi_language
		capital = lhaq_temish

		include = "amerindian_northwest_coast"
		include = "expl_northwestern_america"
		government = {
			ruler = random
		}
	}

	#Halkomelem
	HLM = {

		own_control_core = {
			katzie nooksack sto_lo sts_ailes stz_uminus whonnock
		}

		court_language = halkomelem_language
		capital = whonnock

		include = "amerindian_northwest_coast"
		include = "expl_northwestern_america"
		government = {
			ruler = random
		}
	}

	#Saanich
	WSN = {

		own_control_core = {
			saanich
		}

		court_language = saanich_language
		capital = saanich

		include = "amerindian_northwest_coast"
		include = "expl_northwestern_america"
		government = {
			ruler = random
		}
	}

	#Squamish
	SQH = {

		own_control_core = {
			squamish
		}

		court_language = squamish_language
		capital = squamish

		include = "amerindian_northwest_coast"
		include = "expl_northwestern_america"
		government = {
			ruler = random
		}
	}

	#K'omoks
	KMK = {

		own_control_core = {
			k_omoks homalco klahoose pentlatch sechelt sliammon
		}

		court_language = k_omoks_language
		capital = k_omoks

		include = "amerindian_northwest_coast"
		include = "expl_northwestern_america"
		government = {
			ruler = random
		}
	}

	#Nootkah
	NOO = {

		own_control_core = {
			ditidaht maaqtusiis ucluelet yuquot
		}

		court_language = nootka_language
		capital = ucluelet

		include = "amerindian_northwest_coast"
		include = "expl_northwestern_america"
		government = {
			ruler = random
		}
	}

	#Kwakiutl
	KWA = {

		own_control_core = {
			ma_amtagila quawshelah tanakteuk tlatlasikwala
		}

		court_language = kwakiutl_language
		capital = ma_amtagila

		include = "amerindian_northwest_coast"
		include = "expl_northwestern_america"
		government = {
			ruler = random
		}
	}

	#Oowekyala
	OOW = {

		own_control_core = {
			oweekeno
		}

		court_language = oowekyala_language
		capital = oweekeno

		include = "amerindian_northwest_coast"
		include = "expl_northwestern_america"
		government = {
			ruler = random
		}
	}

	#Nuxalc
	NUX = {

		own_control_core = {
			nuxalc kitasoo
		}

		court_language = nuxalc_language
		capital = nuxalc

		include = "amerindian_northwest_coast"
		include = "expl_northwestern_america"
		government = {
			ruler = random
		}
	}

	#Heiltsuk
	HLK = {

		own_control_core = {
			heiltsuk
		}

		court_language = heiltsuk_language
		capital = heiltsuk

		include = "amerindian_northwest_coast"
		include = "expl_northwestern_america"
		government = {
			ruler = random
		}
	}

	#Haisla
	HLA = {

		own_control_core = {
			haisla
		}

		court_language = haisla_language
		capital = haisla

		include = "amerindian_northwest_coast"
		include = "expl_northwestern_america"
		government = {
			ruler = random
		}
	}

	#Tsimishian
	TMH = {

		own_control_core = {
			gitxsanimaax k_alii_xkalaan nisga_a sm_algyax
		}

		court_language = tsimshian_language
		capital = sm_algyax

		include = "amerindian_northwest_coast"
		include = "expl_northwestern_america"
		government = {
			ruler = random
		}
	}

	#Xaayda
	XDA = {
		own_control_core = {
			kiis_gwaay gwaay_haanas
		}

		court_language = haida_language
		capital = kiis_gwaay

		include = "amerindian_northwest_coast"
		include = "expl_northwestern_america"
		government = {
			ruler = random
		}
	}

	#Tlingit
	TLG = {

		own_control_core = {
			aa_kw galyax gunaaxoo hinyaa jilkaat keex laaxaayik s_awdaan saanya shee_t_ika shtax_heen
			t_aaku taant_a yaakwdaat yakataga xunaa xutsnoowu
		}

		court_language = tlingit_language
		capital = shee_t_ika

		include = "amerindian_northwest_coast"
		include = "expl_northwestern_america"
		government = {
			ruler = random
		}
	}

#Added V1.3

#Tillamook
	TLK = {
		own_control_core = {
		tillamook
		}

		court_language = salishan_language
		capital = tillamook

		include = "amerindian_northwest_coast"
		include = "expl_northwestern_america"
		government = {
			ruler = random
		}
	}

#Alsea
	ALX = {
		own_control_core = {
		yaquina
		}

		court_language = penutian_language
		capital = yaquina

		include = "amerindian_northwest_coast"
		include = "expl_northwestern_america"
		government = {
			ruler = random
		}
	}

#Coos
	COS = {
		own_control_core = {
		quuiich
		}

		court_language = penutian_language
		capital = quuiich

		include = "amerindian_northwest_coast"
		include = "expl_northwestern_america"
		government = {
			ruler = random
		}
	}

#Nlakpamuk
	NPK = {
		own_control_core = {
		skuppah nlaka_pamux scw_exmx
		}

		court_language = salishan_language
		capital = nlaka_pamux

		include = "amerindian_northwest_interior"
		include = "expl_northwestern_america"
		government = {
			ruler = random
		}
	}

#Lillooet
	LWT = {
		own_control_core = {
		leel_watr_ool tsala_ihmec st_at_imcets
		}
		own_control_conquered = {
		llenllenet_ten
		}

		court_language = salishan_language
		capital = leel_watr_ool

		include = "amerindian_northwest_interior"
		include = "expl_northwestern_america"
		government = {
			ruler = random
		}
	}

#Tsilhqot'in
	TQN = {
	own_control_core = {
		yunesit_in tl_etinqox_t_in tsi_del_del tl_esqox elhdaqox_t_in
		}

		court_language = nadene_language
		capital = yunesit_in

		include = "amerindian_northwest_interior"
		include = "expl_northwestern_america"
		government = {
			ruler = random
		}
	}

#Wet'suwet'en
	WST = {
	own_control_core = {
		wet_suwet_en sguuxs hagwilget witset ts_il_kaz_koh
		}
	our_cores_conquered_by_others = {
	nee_tahi_buhn skin_tyee
	}

		court_language = nadene_language
		capital = wet_suwet_en

		include = "amerindian_northwest_interior"
		include = "expl_northwestern_america"
		government = {
			ruler = random
		}
	}

#Dakelh
	DKL = {
	own_control_core = {
		lheidlit_en yekooche tl_azt_en khelhghubunt_en a_taw_bun_kut_en nak_azdlit_en nat_oot_en nadleh_whuten
		}
	our_cores_conquered_by_others = {
	goat_creek nadleht_en nazkot_en lhoosk_uzt_en ulkatchot_en nechakot_en cheslattat_en saik_uz
	}

		court_language = nadene_language
		capital = nadleh_whuten

		include = "amerindian_northwest_interior"
		include = "expl_northwestern_america"
		government = {
			ruler = random
		}
	}

#Secwépemc
	SWP = {
		own_control_core = {
		tk_emlups stil_qw qw_ewt simpcw st_uxwtews
		}
		our_cores_conquered_by_others = {
		llenllenet_ten sk_atsin skitsetsen splatsin mica_creek kinbasket karluk_peak moose_river monashee cariboo xat_sull sexqeltqin llenllenet_ten stswecen_c esk_el crescent_spur willmore hutton lanezi
		}

		court_language = salishan_language
		capital = tk_emlups

		include = "amerindian_northwest_interior"
		include = "expl_northwestern_america"
		government = {
			ruler = random
		}
	}

#Syilix
	SLX = {
		own_control_core = {
		similkameen osoyoos okanagan
		}
		our_cores_conquered_by_others = {
		spaxomin chelan n_pooh_le
		}

		court_language = salishan_language
		capital = osoyoos

		include = "amerindian_northwest_interior"
		include = "expl_northwestern_america"
		government = {
			ruler = random
		}
	}

#Sinixt
	SNX = {
		own_control_core = {
		enselxcin snk_mip ntiltxitk swarakxen
		}
		our_cores_conquered_by_others = {
		stxtilusten illecillewaet q_espiea
		}

		court_language = salishan_language
		capital = ntiltxitk

		include = "amerindian_northwest_interior"
		include = "expl_northwestern_america"
		government = {
			ruler = random
		}
	}

#Ktunaxa
	KTX = {
		own_control_core = {
		yaqan_nukiy aq_am akisq_nuk akinkumasnuqit
		}
		our_cores_conquered_by_others = {
		aqyam_nup akinka_nup ainu_nik ktunwakanmituk aknuq_uk yakyu_ki kananmituk mokowan okotoks aqanqmi
		}

		court_language = ktanaxa_language
		capital = aq_am

		include = "amerindian_northwest_interior"
		include = "expl_northwestern_america"
		government = {
			ruler = random
		}
	}

#Molalla
	MLA = {
		own_control_core = {
		giiwas meli_lema towarnehiooks tukspush
		}
		own_control_conquered = {
		tayxlama
		}
		our_cores_conquered_by_others = {
		south_molala
		}

		court_language = penutian_language
		capital = giiwas

		include = "amerindian_northwest_interior"
		include = "expl_northwestern_america"
		government = {
			ruler = random
		}
	}

------------------------------------------------------------------------
