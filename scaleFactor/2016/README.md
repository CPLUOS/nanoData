# Scale factors for lepton (2016)

These files are sources of scale factors for leptons. To download them from the source, the CERN/CMS accounts is required.

# Trigger efficiency scale factors

## Single electron

Use `HLT_Ele32_eta2p1_WPTight_Gsf_FullRunRange.root`, histogram `SF`, from [here](https://twiki.cern.ch/twiki/pub/CMS/TopTrigger/HLT_Ele32_eta2p1_WPTight_Gsf_FullRunRange.root)
For more information, see [https://twiki.cern.ch/twiki/bin/viewauth/CMS/TopTrigger#Year_2016](https://twiki.cern.ch/twiki/bin/viewauth/CMS/TopTrigger#Year_2016)

## Single muon

Use `EfficienciesAndSF_Run2016.root`, histogram `IsoMu24_OR_IsoTkMu24_PtEtaBins/abseta_pt_ratio`.
This file is a combination of `EfficienciesAndSF_RunBtoF.root`([here](https://calderon.web.cern.ch/calderon/MuonPOG/2016dataReRecoEfficiencies/trigger/EfficienciesAndSF_RunBtoF.root)) and `EfficienciesAndSF_Period4.root`([here](https://calderon.web.cern.ch/calderon/MuonPOG/2016dataReRecoEfficiencies/trigger/EfficienciesAndSF_Period4.root)). The following is the recipe of the combining.

```
python3 $CMSSW_BASE/src/nano/external/scripts/mergeSFroots.py EfficienciesAndSF_Run2016.root IsoMu24_OR_IsoTkMu24_PtEtaBins/abseta_pt_ratio EfficienciesAndSF_RunBtoF.root 19.691 EfficienciesAndSF_Period4.root 13.583
```

Note that 19.691 /fb is the integrated luminosity in the Run2016B-F periods, while 13.583 /fb is that in the Run2016G-H periods.
For more information, see [https://twiki.cern.ch/twiki/bin/view/CMS/MuonWorkInProgressAndPagResults](https://twiki.cern.ch/twiki/bin/view/CMS/MuonWorkInProgressAndPagResults).

# Lepton efficiency scale factors

## Single electron

Use `2016dataReRecoEfficiencies.root`, histogram `EGamma_SF2D`, from [here](https://twiki.cern.ch/twiki/pub/CMS/EgammaIDRecipesRun2/2016LegacyReReco_ElectronTight.root).
For more information, see [https://twiki.cern.ch/twiki/bin/viewauth/CMS/EgammaIDRecipesRun2#80X_series_80X_Scale_factors_for](https://twiki.cern.ch/twiki/bin/viewauth/CMS/EgammaIDRecipesRun2#80X_series_80X_Scale_factors_for).

## Single muon

Use `Run2016_SF_ID.root`, histogram `NUM_TightID_DEN_genTracks_eta_pt`.
This file is a combination of `RunBCDEF_SF_ID.root` ([here](https://gitlab.cern.ch/cms-muonPOG/MuonReferenceEfficiencies/blob/master/EfficienciesStudies/2016_legacy_rereco/systematic/RunBCDEF_SF_ID.root)) and `RunGH_SF_ID.root` ([here](https://gitlab.cern.ch/cms-muonPOG/MuonReferenceEfficiencies/blob/master/EfficienciesStudies/2016_legacy_rereco/systematic/RunGH_SF_ID.root)). The following is the recipe of the combining.

```
python3 $CMSSW_BASE/src/nano/external/scripts/mergeSFroots.py Run2016_SF_ID.root NUM_TightID_DEN_genTracks_eta_pt RunBCDEF_SF_ID.root 19.691 RunGH_SF_ID.root 13.583
```

For more information, see [https://twiki.cern.ch/twiki/bin/view/CMS/MuonReferenceEffs2016LegacyRereco](https://twiki.cern.ch/twiki/bin/view/CMS/MuonReferenceEffs2016LegacyRereco).


